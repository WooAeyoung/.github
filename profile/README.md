# 우애영

반려동물의 식단과 보호소 운영을 더 명확하고 안전하게 만드는 서비스를 만듭니다.

## 한눈에 보기

| 서비스 | 용도 | 기술 |
| --- | --- | --- |
| **우애영 웹 앱** | 반려동물 급여조합·영양소 분석 | React + Vite, FastAPI |
| **우애영 설치형 앱** | 같은 화면을 Electron으로 패키징 | Electron, PyInstaller |
| **Spring Boot 백엔드** | 핵심 분석·인증·펫·제품·식단 API 이식 | Java, Spring Boot, SQLite |
| **우애영 보호소** | 로스터·영양 경고·급여표·재고·예산 | Next.js, Vercel, Neon Postgres |

## 아키텍처

![우애영 서비스 아키텍처](./architecture.svg?v=20260915-3)

우애영 웹 앱은 브라우저에서 실행되는 React 화면입니다. 현재 기본 분석 API는 FastAPI `:8756`이며, Spring Boot `:8757`은 핵심 흐름을 이식해 검증하는 전환 백엔드입니다. 같은 화면은 Electron 데스크톱 앱으로도 패키징할 수 있습니다. 보호소 운영 웹은 별도 Next.js 서비스로 Vercel에 배포합니다.

## 우애영 웹 앱 급여조합 화면

> 실제 브라우저에서 실행 중인 우애영 웹 앱의 메인 화면입니다.

![우애영 웹 앱 급여조합 화면](./app-screen.svg?v=20260915-3)

반려동물 프로필을 확인하고, 먹이는 사료·간식·영양제를 선택해 하루 급여량을 입력합니다. 하단 메뉴에서 `프로필` · `급여조합` · `영양소 분석` · `제품 추가`를 이동합니다.

## 보호소 웹 화면

![우애영 보호소의 로스터 화면](./shelter-screen.svg?v=20260915-3)

보호소 직원은 접근 키로 로그인한 뒤 `보호 동물 로스터` · `경고 트리아지` · `급여표 인쇄` · `사료 재고` · `예산·기부`를 사용합니다.

## 배포

- 웹 앱: FastAPI 서버가 정적 프론트엔드와 API를 함께 제공
- 설치형 앱: Electron + PyInstaller + electron-builder
- 보호소 웹: Vercel 프로젝트 `shelter`, Neon Postgres 저장소
- 임시 공유: Cloudflare Tunnel

## 프로젝트

- [조직 프로필](https://github.com/WooAeyoung)
- [조직 저장소](https://github.com/WooAeyoung)
- [백엔드 저장소](https://github.com/WooAeyoung/backend)

> 현재 영양 기준·제품·가격 데이터는 기능 검증용 데모입니다. 실제 급여 판단이나 수의학적 처방을 대체하지 않습니다.
