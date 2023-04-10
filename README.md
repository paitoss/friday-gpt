# Friday-GPT

| 이 프로젝트는 GPT 에 R&R을 부여해서 단계 별로 프로그래밍을 진행 시키는 프로젝트입니다.

| ⚠️ (Experimental) 이 프로젝트는 실험 중에 있으며, Open A.I 토큰을 많이 소모할 수 있으므로 개발자의 주의가 필요합니다.

<br/>

## 프로젝트 설명

| 이 프로젝트는 프로그래밍을 GPT에게 시키되 각각 단계 별로 A.I에게 R&R 을 부여합니다.

| Architect -> Tech Evangelist -> (Lead -> Junior -> QA -> Senior)

1. Architect R&R - 최초 기획 설계를 담당합니다. 개발 기획 퀄리티초 가 높아질때까지 최대 10회까지 회의를 진행합니다. (src/architect)
2. Tech Evangelist - 아키텍트가 완성한 기획안을 토대로 프로젝트 스펙 및 참조 기술 목록을 작성합니다. (src/evangelist)
3. Lead - 최초 프로그래밍을 진행하고 실제 이용자에게 리뷰를 요청한 후,
4. Junior - 테스트 스크립트를 작성하고 개발된 기능을 안정적이게 하는 방향을 모색해서 보완 개발합니다.
5. QA - 실제 테스트 결과를 받아보고 (현재는 typescript 한정 테스트 지원), 테스트 결과와 원인 및 해결법을 분석한 보고서를 생성합니다.
6. Senior - 작성된 프로그램과 발생된 오류와 QA 보고를 읽은 후 스크립트를 수정해서 에러 해결시도합니다.


| Lead 부터 Senior 까지의 과정은 실제 테스트를 모두 통과할 때 까지 반복됩니다.

| (현재 Junior, QA, Senior 단계는 개발 중에 있습니다.)

<br />

## 프로젝트 실행 방법

| 아래 명령어를 입력해서 프로젝트를 클론한 후 인스톨 해주세요. (이 프로젝트에는 Node.JS 가 필요합니다.)

```bash
git clone https://github.com/hmmhmmhm/friday-gpt
cd ./friday-gpt
npm i
```

| .env 파일을 프로젝트 상단에 생성한 후 아래 내용을 체워줍니다.

```bash
OPENAI_API_KEY=
AZURE_SPEECH_KEY=
AZURE_SPEECH_REGION=
AZURE_SPEECH_VOICE=ko-KR-SeoHyeonNeural
```

| src/input.ts 파일을 열어서 userRequest 변수에 원하는 개발 방향을 설정합니다.

```ts
export const userRequest =
  "문자열로 두 개의 숫자 값을 입력 받아서 마치 사람이 계산하는 방법처럼 각 단위의 숫자를 비교해서 무제한 길이로 사칙연산을 할 수 있는 Typescript 라이브러리를 작성해줘";
```

| 아래 명령어를 실행해서 A.I에게 요청을 보냅니다.

```
npm run dev
```

| 모든 결과파일은 result 폴더 안에 생성됩니다.

<br />

## 라이센스

| MIT Licensed.