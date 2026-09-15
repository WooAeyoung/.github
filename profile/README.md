# 우애영

반려동물의 식단과 보호소 운영을 더 명확하고 안전하게 만드는 서비스를 만듭니다.

## 서비스 구성

| 서비스 | 용도 | 기술 |
| --- | --- | --- |
| **우애영 웹 앱** | 급여조합·영양소 분석 | React + Vite, FastAPI |
| **우애영 설치형 앱** | 같은 화면을 데스크톱으로 패키징 | Electron, PyInstaller |
| **Spring Boot 백엔드** | 핵심 분석·인증·펫·제품·식단 API | Java, Spring Boot, SQLite |
| **우애영 보호소** | 로스터·경고·급여표·재고·예산 | Next.js, Vercel, Neon Postgres |

## 아키텍처

![우애영 서비스 아키텍처](https://raw.githubusercontent.com/WooAeyoung/.github/main/profile/architecture-v2.svg)

우애영 웹 앱은 브라우저에서 실행되는 React 화면입니다. 기본 분석 API는 FastAPI `:8756`, 전환 검증 백엔드는 Spring Boot `:8757`입니다. 보호소 운영 웹은 별도 Next.js 서비스로 Vercel에 배포합니다.

## 주요 화면

<table>
<tr>
<td width="25%" align="center"><img src="https://raw.githubusercontent.com/WooAeyoung/.github/main/profile/login-screen.svg" alt="우애영 로그인 화면" /></td>
<td width="25%" align="center"><img src="https://raw.githubusercontent.com/WooAeyoung/.github/main/profile/app-screen-v2.svg" alt="우애영 급여조합 화면" /></td>
<td width="25%" align="center"><img src="https://raw.githubusercontent.com/WooAeyoung/.github/main/profile/analysis-screen.svg" alt="우애영 영양소 분석 화면" /></td>
<td width="25%" align="center"><img src="https://raw.githubusercontent.com/WooAeyoung/.github/main/profile/shelter-screen-v2.svg" alt="우애영 보호소 로스터 화면" /></td>
</tr>
<tr>
<td align="center"><b>로그인</b><br />이메일 계정으로 시작합니다.</td>
<td align="center"><b>급여조합</b><br />사료·간식·영양제와 하루 급여량을 관리합니다.</td>
<td align="center"><b>영양소 분석</b><br />총량과 참고 범위, 확인 필요 신호를 보여줍니다.</td>
<td align="center"><b>보호소 로스터</b><br />동물·케이지·상태·영양 경고를 관리합니다.</td>
</tr>
</table>

## 운영 흐름

`프로필` → `급여조합` → `영양소 분석` → `제품 추가`

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
