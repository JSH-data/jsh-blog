---
{"dg-publish":true,"permalink":"/next-js/next-js/"}
---


#### Introduction
Next.js 13 버전에서 새롭게 추가된 App Router에는 기존 Pages Router에는 없었던 새로운 기능들이 대거 추가되었습니다. 
이번 시간에는 App Router와 함께 등장한 Next.js의 다양한 라우팅 기술을 알아보겠습니다.  
#### Body
##### Template and Layout Component
Template 파일은 하위 Layout 또는 페이지를 래핑한다는 점에서 Layout과 유사합니다. 
하지만 Layout과 달리 페이지 이동 시 각 하위 Layout에 대해 새로운 인스턴스를 만듭니다. 
- 만약 Suspense를 사용하여 fallback을 표시하는 경우 Layout은 최초 로드시에만 fallback이 적용되지만 Template은 모든 이동에 fallback이 표시됩니다. 
```tsx
// app/template.tsx
// 레이아웃 선언과 동일합니다. 
export default function Template({ children }: { children: React.ReactNode }) {
	return <div>{children}</div>
}
```
##### Route Groups
- app 디렉토리에서 폴더의 중첩은 URL 경로에 매핑됩니다. 하지만 **Route Group을 활용하면 폴더를 URL에 포함시키지 않으면서 파일을 Grouping 할 수 있습니다.** 
- Route Groups를 사용하는 경우 **Root Layout을 여러개 만드는 것이 가능합니다.** 
- 폴더의 이름 "()"로 감싸는 것으로 Route Groups을 만들 수 있습니다. 
![Screenshot 2024-04-16 at 4.54.21 PM.png|center|200](/img/user/assets/Screenshot%202024-04-16%20at%204.54.21%20PM.png)
##### Private Folder
- Private Folder는 폴더 이름 앞에 밑줄을 붙여 만들 수 있습니다 `_folderName`
- Private Folder는 해당 폴더 및 모든 하위 폴더를 라우팅에서 제외시킵니다. 
##### Parallel Routes
- Parallel Routes를 활용하여 **레이아웃 내에서 하나 이상의 페이지를 동시에 혹은 조건부로 렌더링할 수 있습니다.** 
- Parallel Routes는 **slots**를 활용하여 제작할 수 있습니다. 
	- slots는 `@folderName` 컨벤션을 통해 생성가능합니다. ![Pasted image 20240416170348.png|center|600](/img/user/assets/Pasted%20image%2020240416170348.png)
	- slots를 활용하는 경우 부모 레이아웃에 폴더 이름으로 접근이 가능합니다.
```tsx
export default function Layout({ 
	children, 
	team, 
	analytics,
}: {
	children: React.ReactNode,
	analytics: React.ReactNode,
	team: React.ReactNode
}) {
	return (
		<>
			{children}
			{team}
			{analytics}
		</>
	)
}
```
##### Intercepting Routes
- **Interception Routes**는 현재 레이아웃 내에서 다른 경로에 존재하는 컴포넌트를 랜더링 할 수 있도록 도와줍니다. 
	- 이는 컨텍스트의 전환 없이 다른 경로의 콘텐츠를 표시하는 경우에 유용할 수 있습니다. 
- 폴더의 이름 앞에 경로 표시인 "(.)"을 추가하여 Intercepting Routes를 만들 수 있습니다. 
	- `(.)` 동일한 경로
	- `(..)` 한 단계 위의 경로
	- `(..)(..)` 두 단계 위의 경로
	- `(...)` app directory 경로
	![Pasted image 20240416171059.png|center|400](/img/user/assets/Pasted%20image%2020240416171059.png)
- 아래의 예시의 경우 `(.)i/flow/login`는 `i/flow/login` 경로를 대체할 수 있습니다. 
![Screenshot 2024-04-16 at 5.11.49 PM.png|center|300](/img/user/assets/Screenshot%202024-04-16%20at%205.11.49%20PM.png)