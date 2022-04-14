# Vue.js 시작하기

## using CDN

### 강의

```
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

### Vue.js 홈페이지

```
<script src="https://unpkg.com/vue@3"></script>

<div id="app">{{ message }}</div>

<script>
  Vue.createApp({
    data() {
      return {
        message: 'Hello Vue!'
      }
    }
  }).mount('#app')
</script>
```

## 목차

- Vue.js의 이해
  - MVVM
  - Reactivity
  - vue.js developer tool
- 인스턴스 instance
- 컴포넌트 component
  - 전역 컴포넌트
  - 지역 컴포넌트
- 컴포넌트 통신
  - props (parent -> child)
  - event emit (child -> parent)
- 라우터 router
- HTTP 비동기 통신 (using axios)
- 템플릿 template 문법
  - data binding with mustache (=보간법 interpolation)
  - 디렉티브 custom directives
    - v-if/v-else
    - v-bind
    - v-on:eventType
    - v-show
    - v-model
    - 수식어 modifier
- 프로젝트 생성 도구 Vue CLI
- 싱글 파일 컴포넌트
- 최종 프로젝트 : 사용자 입력 폼 만들기
