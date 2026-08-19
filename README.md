# Kaya Utils

한글(HWP)·엑셀·워드 문서를 다루는 작은 도구 모음입니다.

**여기는 배포처입니다.** 소스는 들어 있지 않고 실행 파일만 올라옵니다
([왜 그런지](#소스가-없는-이유)).

- 웹: **kayautils.com** *(준비 중)*
- 내려받기: [Releases](../../releases)
- 버그·건의: [Issues](../../issues)

---

## 도구

### `kayatext` — 문서에서 텍스트를 뽑습니다

AI 에 문서를 넣으려면 먼저 텍스트로 만들어야 하고, **검색 품질은 구조가 남아
있느냐로 갈립니다.** 표가 줄글로 뭉개지면 검색이 틀리고, 제목이 없으면 문서를
자를 경계를 잡을 수 없습니다.

그래서 기본 출력이 Markdown 입니다. 표는 `|` 표로, 시트는 `##` 제목으로 나갑니다.

```bash
kayatext 회의록.hwp                  # 회의록.md 로
kayatext *.hwp *.xlsx -o out/        # 여러 개를 한 폴더로
kayatext 문서.hwp --txt              # 순수 텍스트로
kayatext 문서.hwp -                  # 표준 출력으로 (파이프용)
```

받는 형식 — `.hwp` `.hwpx` `.hml` `.xlsx` `.xlsm` `.docx` `.rtf`

**HWP 가 핵심입니다.** docx·pdf 는 이미 읽어 주는 도구가 많지만, 한글 문서는
그렇지 않습니다. 국내 공공문서는 대부분 HWP 입니다.

| | |
|---|---|
| macOS (Apple Silicon) | ✅ |
| Windows (x64) | 준비 중 |
| Linux (x64, musl) | 준비 중 |
| macOS (Intel) | 후순위 |

### `KayaPDF` — 문서를 PDF 로 바꾸고 합칩니다 *(준비 중)*

HWP·엑셀 문서를 PDF 와 고칠 수 있는 형식으로 바꾸고, 챕터별 문서를 하나의 PDF 로
합치고, 폴더 단위로 일괄 처리하는 데스크톱 앱입니다.

---

## 라이선스

**오픈소스가 아닙니다.** 배포물에 들어 있는 `LICENSE.txt` 가 전문입니다.

| | |
|---|---|
| 개인 · 학습 · 연구 · 비영리 | **무료** |
| 법인 · 공공기관의 도입 검토 | **무료** |
| 법인 · 공공기관의 계속적인 업무 사용 | 기업 라이선스 |

**기능 제한은 없습니다.** 무료로 쓰든 기업 라이선스로 쓰든 되는 일이 같습니다.
사용량을 세거나 기능을 잠그는 코드는 들어 있지 않습니다. 기업 라이선스로 받는
것은 **적법한 사용 권리와 그 증빙**입니다.

**재배포는 금지합니다.** 다른 사람이 받아 갈 수 있는 곳에 설치 파일을 올려 두는
것도 여기 포함됩니다 — 사내 공유 폴더, 파일 서버, 그룹웨어 자료실, 웹하드, 공유
설정된 클라우드 드라이브가 모두 해당합니다. 알려 주실 때는 파일 대신 이 저장소
주소를 전해 주세요.

조직 안에 배포해야 하는 사정이 있으시면 이슈로 알려 주시면 별도 조건을 협의할 수
있습니다.

**만든 결과물에는 아무 제한이 없습니다.** 이 도구로 뽑은 텍스트·Markdown·PDF 는
전적으로 여러분의 것입니다.

### 오픈소스 고지

포함된 오픈소스 구성 요소는 각자의 라이선스를 따릅니다. 배포물의
`THIRD-PARTY-NOTICES.md` 에 전문이 있고, 실행 파일 안에도 들어 있습니다.

```bash
kayatext --licenses
```

특히 HWP 변환은 [rhwp](https://github.com/edwardkim/rhwp)(MIT) 위에 서 있습니다.
그 프로젝트가 없었으면 이 도구도 없었습니다.

---

## 소스가 없는 이유

개인이 만드는 도구이고, 재배포를 막는 쪽을 골랐습니다. 받아 가는 길이 한 곳이어야
어떤 버전이 돌아다니는지 알 수 있고, 문제가 생겼을 때 고친 것이 실제로 전달됩니다.

대신 **열어 두는 것들이 있습니다.**

- **웹 도구의 소스**는 공개합니다. 「파일이 서버로 가지 않습니다」는 주장은
  확인할 수 있어야 의미가 있습니다
- **다른 오픈소스에 낸 기여**와 그 근거는 공개합니다
- **조사 과정에서 알아낸 것들**(HWPX 규격의 함정 같은 것)을 정리해 올립니다.
  같은 곳에서 막히는 사람이 다시 헤매지 않도록

---

## 도와주실 수 있는 것

### 안 되는 문서를 알려 주세요

저희가 만든 시험용 파일로는 잡히지 않는 버그가 있습니다. **실제 문서에만 있는
것들** 때문입니다 — 11열 병합, 도형이 섞인 표, 오래된 한글로 만든 서식.

**가장 도움이 되는 것은 공개된 정부·공공기관 문서입니다.** 공고문, 서식,
보도자료 — 파일을 보내실 필요 없이 **내려받을 수 있는 주소만** 알려 주시면 됩니다.

### 회사 문서라면 — 올리지 마세요

업무 문서에는 이름·연락처가 들어 있고 **작성자는 파일 정보에도 남습니다.**
공개된 곳에 올리면 되돌릴 수 없고, 올리신 분이 곤란해질 수 있습니다.

대신 **증상만** 적어 주세요. 「표가 있는 3쪽짜리 공문인데 2쪽부터 선이 사라진다」
정도면 비슷한 파일을 만들어 재현합니다. 꼭 파일이 필요하면 비공개로 주고받고,
익명화 방법을 안내드립니다.

### 감사의 표시

보내 주신 것이 실제로 버그를 잡았거나 회귀 시험에 들어가면 —

- 회귀 시험 목록에 이름을 올립니다 (원하시면)
- **기업 라이선스를 무상으로 드립니다.** 회사에서 쓰셔야 하는 분께 값이 될 겁니다.
  개인·학습용은 원래 무료라 따로 드릴 것이 없습니다

라이선스를 받으려고 무리해서 파일을 보내지는 마세요.
**주소 하나가 파일 열 개보다 낫습니다.**

---

## English

**Kaya Utils** — small tools for Korean office documents.

`kayatext` extracts text and Markdown from HWP (the Korean word processor format),
Excel, Word, and RTF files, so they can be fed to AI pipelines with their tables and
headings intact. HWP is the point: most other formats already have good extractors,
Korean public-sector documents do not.

**This repository ships binaries only — it is not open source.** Free for personal,
educational, non-profit, and evaluation use, with **no functional limits whatsoever**.
A commercial license is required for ongoing business use by companies and public
institutions; it grants the right to use and the paperwork to prove it, not extra
features. Redistribution — including placing the installer on a shared drive or file
server — is not permitted; please share this repository's address instead. Whatever
you produce with it is entirely yours.

Bundled open-source components remain under their own licenses; run
`kayatext --licenses` or see `THIRD-PARTY-NOTICES.md` in the download. HWP support is
built on [rhwp](https://github.com/edwardkim/rhwp) (MIT).

Bug reports are welcome. **Please do not attach real work documents** — they carry
personal data, and author names survive in file metadata. Describe the symptom, or
link to a publicly published government document that reproduces it.

---

Copyright © 2026 가야태자 (kjh0523). All rights reserved.
