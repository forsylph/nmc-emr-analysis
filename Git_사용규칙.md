# EMR 프로젝트 Git 사용 규칙

**관리자**: PM (프로젝트 매니저)  
**시행일**: 2026-02-16  
**대상**: EMR 프로젝트팀 전원 (28명)

---

## 📁 디렉토리 구조

```
nmc-emr-analysis/
├── .git/                   # Git 저장소
├── .gitignore             # 무시 파일 설정
├── README.md              # 프로젝트 개요
├── analysis/              # 화면 분석서
│   ├── SMRPE/            # 채용/인사
│   ├── SMPMO/            # 외래진료
│   ├── SMPMI/            # 입원/처방
│   ├── MMO/              # 처방/오더
│   └── SPR/              # 공통 팝업
├── design/               # React 설계안
├── scripts/              # 자동화 스크립트
├── reports/              # 보고서
└── docs/                 # 문서/가이드
    └── templates/        # 분석 템플릿
```

---

## 📝 파일 저장 규칙

### analysis/ (화면 분석서)
| 도메인 | 폴더 | 화면ID 예시 |
|--------|------|------------|
| 채용/인사 | `SMRPE/` | SMRPE01000, SPRPE01002 |
| 외래진료 | `SMPMO/` | SMPMO00200, SMPMO00300 |
| 입원/처방 | `SMPMI/` | SMPMIxxx |
| 처방/오더 | `MMO/` | MMOxxx |
| 공통 팝업 | `SPR/` | SPRPE01002, SPRPE01003 |

**파일명 형식**:
```
[화면ID]_[화멸명]_[작성자]_분석.md

예시:
- SMRPE01000_입사지원서등록_개발자A1_분석.md
- SMPMO00200_외래접수_리더B_분석.md
- SPRPE01002_부서코드팝업_주니어A1_분석.md
```

### design/ (React 설계안)
```
[화면ID]_React설계안_[작성자].md

예시:
- SMRPE01000_React설계안_시디.md
```

### reports/ (보고서)
```
[보고유형]_[시각]_[작성자].md

예시:
- PM_간략보고_0810.md
- 건강체크_0500.md
```

---

## 🔧 Git 워크플로우

### 1. 작업 시작
```bash
# 1. 최신 코드 받기
git pull origin main

# 2. 새 브랜치 생성 (선택사항)
git checkout -b feature/SMRPE01000
```

### 2. 작업 완료 후
```bash
# 1. 변경사항 확인
git status

# 2. 파일 추가
git add analysis/SMRPE/SMRPE01000_입사지원서등록_개발자A1_분석.md

# 3. 커밋 (규칙 준수)
git commit -m "[SMRPE01000] 입사지원서등록 분석 완료 - 개발자A1"

# 4. 푸시
git push origin main
# 또는 브랜치 사용 시: git push origin feature/SMRPE01000
```

### 3. 커밋 메시지 규칙
| 작업 유형 | 메시지 형식 | 예시 |
|-----------|------------|------|
| 분석 완료 | `[화면ID] 화멸명 분석 완료 - 작성자` | `[SMRPE01000] 입사지원서등록 분석 완료 - 개발자A1` |
| 리뷰 완료 | `[리뷰] 화면ID 결과 - 작성자` | `[리뷰] SMRPE01000 Pass - 피디` |
| 수정 | `[수정] 화면ID 내용 - 작성자` | `[수정] SMRPE01000 EJB 추가 - 개발자A1` |
| 보고서 | `[보고] 보고유형 시각 - 작성자` | `[보고] PM_간략보고_0810 - PM` |

---

## ⚠️ 주의사항

### 금지 사항
- ❌ API 토큰/비밀번호 커밋 (GitHub 보안 정책 위반)
- ❌ 개인 설정 파일 커밋 (.env, .local 등)
- ❌ 바이너리/실행 파일 커밋

### .gitignore 설정
```
# 환경 변수
.env
.env.local

# API 토큰 (TOOLS.md에서 관리)
*token*
*secret*

# 개인 설정
.DS_Store
.vscode/
.idea/

# 임시 파일
*.tmp
*.log
```

---

## 📋 체크리스트 (작업 완료 시)

- [ ] 분석 완료
- [ ] 마크다운 파일 작성 (analysis/ 폴더에 저장)
- [ ] 파일명 규칙 준수
- [ ] Git add
- [ ] Git commit (메시지 규칙 준수)
- [ ] Git push
- [ ] 노션 업로드
- [ ] PM 보고

---

## 🎯 산출물 정책 (Sir 지시)

> **"작업 후 보고서 없음 = 미완료 = 다시 하라"**

**필수 3단계**:
1. ✅ 마크다운 보고서 작성 (`analysis/` 폴더)
2. ✅ Git 커밋 & 푸시
3. ✅ 노션 업로드 (`306d775a6134800d9d42dded5a0b82b3`)

**보고서 없는 작업은 인정되지 않습니다!**

---

**작성**: PM  
**최종수정**: 2026-02-16
