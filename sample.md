










## Tailwindcss 설정



## 깃허브 룰 설정

### develop 브랜치 생성
#### 기본으로 지정
### 브랜치 생성
- 모든 작업은 브랜치를 만들어서 진행

### PR 템플릿
















### 커밋 컨벤션(Commit Convention)

Git 커밋을 작성할 때 커밋 메시지에 관한 컨벤션을 구성하여 활용하면 보다 일관성 있고 가독성 높은 커밋을 작성할 수 있습니다. 참고: [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/)

다음은 커밋 컨벤션 타입 및 커밋 메시지 예시입니다.

| 타입        | 설명                           |
|-------------|--------------------------------|
| Feat:      | 새로운 기능 추가              |
| BugFix:    | 버그 수정                     |
| Docs:      | 문서의 수정                   |
| Modify:    | 코드 변경                     |
| Refactor:  | 리팩토링                      |
| Design:    | CSS 등 사용자 UI 디자인 변경   |
| Comment:   | 필요한 주석 추가 및 변경      |
| Style:     | 코드 포맷팅, 세미콜론 누락 등 |
| Test:      | 테스트 관련                   |
| Chore:     | 빌드 수정, 패키지 매니저 설정 |
| Init:      | 프로젝트 초기 생성            |
| Rename:    | 파일 또는 폴더명 수정        |
| Remove:    | 파일 삭제                     |
| Merge:     | Pull 과정 중 자동 병합        |
| Build:     | 새로운 라이브러리 또는 패키지  |

커밋 메시지 형식은 다음과 같습니다.

```
<type>[optional scope]: <description>

[optional body]

[optional footer(s)]
```

커밋 메시지는 subject, body, footer로 구성되어 있습니다.

```
type: Subject -> 제목  
(빈줄)  
body(Optional) -> 본문  
(빈줄)  
footer(생략 가능) -> 꼬리말
```

### 코딩 컨벤션(Coding Convention)

코딩 컨벤션은 여러 명의 개발자가 협업을 할 때 코드를 읽고, 관리하기 쉽도록 도와주는 코딩 스타일 규칙을 의미합니다. HTML5와 자바스크립트의 문법 유연성으로 인해 통일된 규칙 준수가 필요합니다.

- [구글 HTML/CSS 코딩 컨벤션](https://google.github.io/styleguide/htmlcssguide.html)
- [구글 Javascript 코딩 컨벤션](https://google.github.io/styleguide/jsguide.html)
- [Airbnb JavaScript 스타일 가이드](https://github.com/tipjs/javascript-style-guide)
- [NHN 코딩 컨벤션](https://nuli.navercorp.com/tool/codingCon)
- [TOAST UI Javascript 코딩 컨벤션](https://ui.toast.com/fe-guide/ko_CODING-CONVENTION#%EB%AA%A8%EB%93%88)

### 위키(Wiki)

GitHub Wiki는 GitHub 저장소의 일부로, 프로젝트 팀원들이 프로젝트와 관련된 정보를 쉽게 공유하고 문서화할 수 있는 플랫폼입니다. Wiki 문서는 마크다운으로 쉽게 작성이 가능하며, 프로젝트의 지식을 공유하고 기록하는 데 도움이 됩니다. ([Wiki 사례](https://github.com/Devfolio-team/Devfolio-Client/wiki))

### 위키 생성 및 편집

프로젝트 저장소에 Wiki 항목을 선택하여 Create the first page → Save page를 클릭하여 Wiki를 생성합니다.

HOME과 함께 푸터와 사이드바도 추가하면 다음과 같은 모습이 됩니다.

Wiki에 마크다운 문서를 추가하거나 편집하고자 할 때, GitHub에서 작업하기보다 해당 저장소를 로컬에서 작업하고자 한다면 Clone this wiki locally 항목에서 URL을 복사하여 로컬로 clone합니다.

클론한 저장소에서 데일리 스크럼, 리뷰, 회고 등의 문서를 추가, 수정, 삭제 후 커밋하여 GitHub Wiki 저장소로 푸시하여 프로젝트에 대한 기록을 문서화합니다.


# 프로젝트 생성에서 배포까지

- 목차

## Vite란?

[Vite](https://vitejs.dev/)는 Frontend Frameword인 Vue의 창시자 Evan You가 만든 새로운 프론트엔드 [번들링 도구](https://tech.weperson.com/wedev/frontend/bundling-transpiler/#%E1%84%87%E1%85%A5%E1%86%AB%E1%84%83%E1%85%B3%E1%86%AF%E1%84%85%E1%85%A5-bundler)로 프랑스어로 "빠르다(Quick)"라는 의미를 가집니다. Vite는 번들링을 위해 내부적으로 [Rollup](https://rollupjs.org/)과 [esbuild](https://esbuild.github.io/)를 사용하며 기존 번들러의 강자였던 [Webpack](https://webpack.js.org/)보다 수십배 이상 빨라 모던 웹 환경에서 효율적인 개발을 가능케 해줍니다.

## Vite/Github

**Step-1** 

배포 테스트를 위한 로컬 저장소를 다음과 같이 생성합니다.

```bash
npm create vite@latest
```

- project-name : vite-netlify
- framework : Vanilla
- variant: Javascript

**Step-2**

로컬 저장소가 생성되면 저장소로 이동 후 다음의 명령을 입력합니다.

```bash
cd <프로젝트 폴더>
```

```bash
npm install
```

```bash
npx add-gitignore node,windows,osx,visualstudiocode
```

```bash
echo '# Vite + Netlify' > README.md
```

```bash
git init
```

```bash
git add .
```

```bash
git commit -m "배포를 위한 초기 환경구성"
```

**Step-3**

로컬 저장소 생성 및 main 브랜치에 초기 환경구성이 마무리 되었다면 배포를위한 리모트 저장소를 생성합니다. 
(리모트 저장소에 README.md, .gitignore 파일이 생성되지 않도록 주의하시기 바랍니다.)

![스크린샷 2023-12-14 오전 10.27.51.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/005e8b9d-b53b-4f05-baaa-c6de1cbdf01b/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_10.27.51.png)

**Step-4**

리모트 저장소 생성이 완료되었다면 로컬 컴퓨터에 리모트 저장소를 추가하고 main 브랜치를 리모트 저장소로 push 합니다.

```bash
git remote add origin https://github.com/<Github ID>/<리모트저장소 URL>
```

```bash
git push --set-upstream origin main
```


**Step-5**

로컬 저장소에 기능 개발 및 구현을 위한 develop 브랜치를 생성한 후 새로운 커밋을 추가하고 리모트 저장소에 push 합니다.

```bash
git checkout -b develop
```

```bash
echo '## Netlify 배포 준비' >> README.md
```

```bash
git add .
```

```bash
git commit -m "develop 브랜치 생성 및 README 수정"
```

```bash
git push --set-upstream origin develop
```

**Step-6**

리모트 저장소의 main 브랜치의 경우 PR을 이용한 merge 이외에는 변경되지 않도록 브랜치 보호를 설정합니다.

![스크린샷 2023-12-13 오후 8.12.53.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/4ad1ea2d-a2f2-4603-8c81-9c91d327246c/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-13_%E1%84%8B%E1%85%A9%E1%84%92%E1%85%AE_8.12.53.png)

## Netlify

**Step-1**

배포(Deploy)를 위해 Netlify에 로그인 한 후 `Add new site` 버튼을 클릭한 후 `Import an existing project`를 선택합니다.

![스크린샷 2023-12-14 오전 10.43.28.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/1fc0db73-44e1-4dd4-b5a1-beebc0186d99/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_10.43.28.png)

**Step-2**

**Let's deploy your project** 항목에서 `Deploy with Github`을 선택합니다.

![스크린샷 2023-12-14 오전 10.45.10.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/0053ead5-d3a9-4d98-a4b5-7e9243d88050/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_10.45.10.png)

**Step-3**

배포하고자 하는 Github 저장소를 검색한 후 해당 저장소를 선택합니다.

![스크린샷 2023-12-14 오전 10.47.05.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/a2610d00-b2cc-4cf7-817c-e26f6d9ce1d1/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_10.47.05.png)

**Step-4**

배포를 위한 정보를 다음과같이 입력한 뒤 `Deploy` 버튼을 선택합니다.

![스크린샷 2023-12-14 오전 10.50.04.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/aeac93df-e1d8-4119-abc8-38e8f75eb234/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_10.50.04.png)

**Step-5**

URL을 클릭하면 배포된 결과를 확인할 수 있습니다.

![스크린샷 2023-12-14 오전 10.55.33.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/ba46c4cd-4e5f-4262-9e71-13b080ca8e51/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_10.55.33.png)

`Site configuration` 버튼을 클릭한 후 **Site information → Change site name에서** 배포 URL의 이름을 변경할 수 있습니다. 

![스크린샷 2023-12-14 오전 10.59.54.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/3cc08ddb-4f3e-49ed-8083-dc82feced48c/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_10.59.54.png)

## CI/CD

CI/CD (Continuous Integration/Continuous Delivery)는 **애플리케이션 개발 단계를 자동화하여 애플리케이션을 더욱 짧은 주기로 고객에게 제공하는 방법**입니다. CI/CD의 기본 개념은 지속적인 통합, 지속적인 서비스 제공, 지속적인 배포입니다.

**Step-1**

배포 업데이트를 위해  로컬 저장소의 `delvolp` 브랜치에서 파일을 수정한 후 커밋을 완료하고 리모트 저장소로 push 합니다.

main.js

```bash
<h1>Hello Vite + Netlify</h1>
```

```bash
git add .
```

```bash
git commit -m "메인 페이지 제목 수정"
```

```bash
git push
```

**Step-2**

develop 브랜치의 변경사항을 main 브랜치로 merge하기 위해 PR을 생성합니다.

![스크린샷 2023-12-14 오전 11.10.53.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/e8fd40f4-200f-4503-a3a9-0eeae71d39d9/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_11.10.53.png)

**Step-3**

Open된 PR을 선택한 후 Merge pull request 버튼을 클릭하여 merge를 완료합니다.

![스크린샷 2023-12-14 오전 11.11.52.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/6cd9a5f5-47e5-49b8-9e3c-3436f1434f8d/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_11.11.52.png)

![스크린샷 2023-12-14 오전 11.12.06.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/14b3c8f3-75fe-4a37-b567-cd7fa9e156d6/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_11.12.06.png)

**Step-4**

Close된 PR을 클릭하면 배포 결과를 미리보기 할 수 있는 URL과 QR Code를 통해 업데이트를 확인할 수 있습니다. (기존 배포된 URL로도 업데이트를 확인할 수 있습니다.)

![스크린샷 2023-12-14 오전 11.15.57.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/2c9b0f24-8e73-4514-b0c2-312f3d7d31f4/cf0480a4-1ddc-4226-a4a8-e23ed94b6c42/%E1%84%89%E1%85%B3%E1%84%8F%E1%85%B3%E1%84%85%E1%85%B5%E1%86%AB%E1%84%89%E1%85%A3%E1%86%BA_2023-12-14_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_11.15.57.png)

```bash
import { resolve } from 'path'
import { defineConfig } from 'vite'

const root = resolve(__dirname, 'src');
const outDir = resolve(__dirname, 'docs');

export default defineConfig({
  root,
  publicDir: '../public',
  build: {
    outDir,
    emptyOutDir: true,
    rollupOptions: {
      input: {
        main: resolve(root, 'index.html'),
        home: resolve(root, 'pages/login', 'index.html'),
      },
    },
  },
});
```

## Vite + Tailwindcss

Vite환경에서 Tailwindcss 패키지를 설치하고 Multi Page를 서비스하기 위한 셋팅을 알아보도록 하겠습니다. 

Vite 프로젝트를 생성하기 위해 다음의 명령을 입력하고 project-name, framework, variant를 설정합니다.

```bash
npm create vite@latest
```

- project-name : vite-tailwind
- framework : Vanilla
- variant: Javascript

프로젝트 폴더가 생성되면 해당 폴더로 이동합니다. 

```bash
cd vite-tailwind
```

vite 환경 구축을 위한 패키지를 설치합니다.

```bash
npm install
```

다음 명령을 통해 TailwindCSS 패키지를 설치 합니다.

```bash
npm install -D tailwindcss postcss autoprefixer
```

PostCSS와 TailwindCSS 환경 설정 파일 생성을 위해 다음 명령을 입력합니다.

```bash
npx tailwindcss init -p
```

HTML 파일을 컴파일 하기 위한 작업 경로를 tailwind.config.js 파일에 다음과 같이 지정합니다.

```bash
export default {
  content: [
    "./**/*.{js,html}",
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

새파일을 생성하고 파일 이름은 vite.config.js로 지정합니다.

```bash
touch vite.config.js 
```

Multi Page 빌드를 위해 vite.config.js 파일에 다음의 코드를 입력합니다.

```jsx
import { resolve } from 'node:path'
import { defineConfig } from 'vite'

export default defineConfig({
  build: {
    outDir:'docs',
    rollupOptions: {
      input: {
        main: resolve(__dirname, 'index.html'),
        login: resolve(__dirname, "./src/pages/login/login.html"),
      },
    },
    
  },
})
```

style.css 파일에 기존 코드를 모두 삭제하고 다음과 같이 입력합니다.

```bash
@tailwind base;
@tailwind components;
@tailwind utilities;
```

main.js 파일에 기존 코드 중 스타일 파일을 연결하기 위한 코드만 남기고 모두 삭제합니다.

```bash
import "./style.css";
```

index.html 파일을 다음과 같이 수정합니다.

pages, pages/login 폴더와 pages/login/index.html 파일을 생성합니다.

```bash
mkdir pages pages/login
touch pages/login/login.html
```

pages/home/login.html 파일에 다음의 코드를 입력합니다.

```html
<!doctype html>
<html lang="ko-KR">
  <head>
    <meta charset="UTF-8" />
    <link rel="icon" type="image/svg+xml" href="/vite.svg" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Vite + TailwindCSS</title>
    <script type="module" src="/main.js"></script>
  </head>
  <body class="bg-yellow-200 flex flex-col justify-center items-center h-screen">
    <h1>Vite에 멀티 페이지 설정하기</h1>
    <img src="/public/vite.svg" alt="" />
		<a href="/index.html">로그인 페이지</a>
  </body>
</html>
```

.gitignore 파일을 생성합니다.

```bash
npx add-gitignore node,windows,osx,visualstudiocode
```

프로젝트 폴더를 git 저장소로 초기화 합니다.

```bash
git init
```

파일 내용에 Vite + TailwindCSS가 추가되도록 README.md 파일을 생성합니다. 

```bash
echo '# Vite + TailwindCSS' > README.md
```

변경 사항에 대한 커밋을 생성하기 위해 프로젝트 폴더의 파일들을 모두 Stage로 올립니다. 

```bash
git add .
```

커밋을 생성합니다.

```bash
git commit -m "Vite + TailwindCSS 초기 환경구성"
```

npm run dev 명령을 입력하고 개발 서버가 구동되면 localhost로 접속해서 렌더링 결과를 확인합니다.

```bash
npm run dev
```

`npm run preview 명령은 npm run build를 실행해서 docs 폴더가 생성되면 해당 폴더가 배포될 때 어떻게 보이는지 확인하기 위한 용도입니다.`

Github에 리모트 저장소를 생성하고 로컬 저장소에 리모트 저장소의 URL을 등록합니다.

```bash
git remote add origin https://github.com/<Github ID>/<리모트저장소 URL>
```

로컬 저장소 main 브랜치의 커밋을 푸시합니다.

```bash
git push --set-upstream origin main
```

배포를 위해 Netlify 서비스에 Github 저장소를 연결하고 Deploy 버튼을 선택합니다.
`(배포 설정 및 develop 브랜치의 변경 내용 반영은 위에 정리해 놓은 Netlify와 CI/CD 부분을 참고하시기 바랍니다.)`
## Netlify

## Vercel


# API 서버

