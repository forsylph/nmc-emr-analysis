# Git 사용규칙 (PM 관리)

**버전**: 1.0  
**작성일**: 2026-02-16  
**작성자**: PM (Sir 지시)  

---

## 📁 디렉토리 구조

```
nmc-emr-analysis/
├── analysis/          # 화면 분석서 (핵심)
│   ├── SMRPE/        # 채용/인사
│   ├── SMPMO/        # 외래진료
│   ├── SMPMI/        # 입원/처방
│   ├── MMO/          # 처방/오더
│   └── SPR/          # 공통 팝업
├── design/           # React 설계안
├── scripts/          # 자동화 스크립트
├── reports/          # 보고서
└── docs/templates/   # 문서 템플릿
```

---

## 📝 파일 저장 규칙

### 분석서 파일명 형식

```
analysis/[도메인]/[화면ID]_[화멸명]_[작성자]_분석.md
```

### 예시

```
analysis/SMRPE/SMRPE01000_입사지원서등록_개발자A1_분석.md
analysis/SMPMO/SMPMO00200_외래접수_리더B_분석.md
analysis/SMPMI/SMPMI00100_입원등록_시니어C1_분석.md
analysis/SPR/SPRPE01002_부서코드팝업_주니어A1_분석.md
```

---

## 💾 Git 커밋 규칙

### 커밋 메시지 형식

```bash
git commit -m "[화면ID] 화멸명 분석 완료 - 작성자"
```

### 예시

```bash
git commit -m "[SMRPE01000] 입사지원서등록 분석 완료 - 개발자A1"
git commit -m "[SMPMO00200] 외래접수 분석 완료 - 리더B"
git commit -m "[SPRPE01002] 부서코드팝업 분석 완료 - 주니어A1"
```

---

## ✅ 산출물 정책 (Sir 지시)

> **"작업 후 보고서 없음 = 미완료 = 다시 하라"**

### 필수 3단계

| 단계 | 산출물 | 위치 | 확인 |
|------|--------|------|------|
| 1 | 마크다운 보고서 | `analysis/[도메인]/` | ⭐ 필수 |
| 2 | Git 커밋 & 푸시 | GitHub | ⭐ 필수 |
| 3 | 노션 업로드 | `306d775a6134800d9d42dded5a0b82b3` | ⭐ 필수 |

**하나라도 빠지면 미완료!**

---

## 🔧 Git 워크플로우

### 1. 분석 완료 후

```bash
# 1. 파일 저장 (analysis/ 폴에)
cp 화멸분석서.md analysis/SMRPE/SMRPE01000_입사지원서등록_개발자A1_분석.md

# 2. Git 추가
git add analysis/SMRPE/SMRPE01000_입사지원서등록_개발자A1_분석.md

# 3. 커밋
git commit -m "[SMRPE01000] 입사지원서등록 분석 완료 - 개발자A1"

# 4. 푸시
git push origin main
```

### 2. 1시간마다 정기 푸시

```bash
# 모든 변경사항 커밋
git add .
git commit -m "[보고] 오전현황 - PM"
git push origin main
```

---

## 📋 체크리스트 (분석 완료 시)

```
□ 1. 마크다운 보고서 작성
   - 파일명: [화면ID]_[화멸명]_[작성자]_분석.md
   - 위치: analysis/[도메인]/

□ 2. Git 커밋
   - git add .
   - git commit -m "[화면ID] 화멸명 분석 완료 - 작성자"
   - git push origin main

□ 3. 노션 업로드
   - 제목: [화면ID]_[화멸명]_[작성자] 보고
   - 부모 페이지: 306d775a6134800d9d42dded5a0b82b3
```

---

## 🚨 주의사항

1. **파일명 오류 금지**: 정확한 형식 준수
2. **위치 오류 금지**: analysis/[도메인]/ 폴에 저장
3. **커밋 메시지 규칙**: `[화면ID] 화멸명 분석 완료 - 작성자`
4. **푸시 필수**: 로컬만 작업 금지, 반드시 GitHub 푸시

---

## 📖 참조

- **GitHub**: https://github.com/forsylph/nmc-emr-analysis
- **Notion**: `306d775a6134800d9d42dded5a0b82b3`

---

**모든 팀원은 본 규칙을 준수해야 합니다!**

**PM 관리 책임하에 운영됩니다.**
