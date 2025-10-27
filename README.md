# 네이버 블로그 자동화 도구

AI를 활용한 네이버 블로그 자동 포스팅 도구입니다. Google Gemini API를 사용하여 콘텐츠를 생성하고, Selenium을 통해 네이버 블로그에 자동으로 포스팅합니다.

## 🚀 주요 기능

- **AI 콘텐츠 생성**: Google Gemini API를 사용한 자동 콘텐츠 생성
- **자동 포스팅**: Selenium을 통한 네이버 블로그 자동 포스팅
- **계정 관리**: 여러 네이버 계정 관리 및 순차 포스팅
- **프롬프트 관리**: 재사용 가능한 프롬프트 템플릿 관리
- **이미지 관리**: 이미지 폴더 등록 및 자동 사용
- **실시간 미리보기**: 생성된 콘텐츠 미리보기 기능

## 📋 요구사항

- Python 3.8 이상
- Chrome 브라우저
- Google Gemini API 키

## 🛠️ 설치 방법

### 1. 저장소 클론

```bash
git clone https://github.com/yourusername/naver-blog-automation.git
cd naver-blog-automation
```

### 2. 가상환경 생성 및 활성화

```bash
# 가상환경 생성
python -m venv venv

# 가상환경 활성화 (Windows)
venv\\Scripts\\activate

# 가상환경 활성화 (macOS/Linux)
source venv/bin/activate
```

### 3. 의존성 설치

```bash
pip install -r requirements.txt
```

또는 개발용 의존성과 함께 설치:

```bash
pip install -e ".[dev]"
```

### 4. 환경변수 설정

#### 방법 1: .env 파일 사용 (권장)

1. `env.example` 파일을 `.env`로 복사:
```bash
cp env.example .env
```

2. `.env` 파일을 열어서 실제 값으로 수정:
```env
# Google Gemini API 설정
GEMINI_API_KEY=your_actual_gemini_api_key_here

# OpenAI API 설정 (선택사항)
OPENAI_API_KEY=your_openai_api_key_here

# 기타 설정...
```

#### 방법 2: 시스템 환경변수 설정

**Windows (PowerShell):**
```powershell
$env:GEMINI_API_KEY="your_actual_gemini_api_key_here"
```

**Windows (Command Prompt):**
```cmd
set GEMINI_API_KEY=your_actual_gemini_api_key_here
```

**macOS/Linux:**
```bash
export GEMINI_API_KEY="your_actual_gemini_api_key_here"
```

### 5. 애플리케이션 실행

```bash
streamlit run main_streamlit.py
```

브라우저에서 `http://localhost:8501`로 접속하여 애플리케이션을 사용할 수 있습니다.

## 🔑 API 키 발급 방법

### Google Gemini API 키

1. [Google AI Studio](https://aistudio.google.com/)에 접속
2. Google 계정으로 로그인
3. "Get API key" 버튼 클릭
4. "Create API key" 선택
5. 생성된 API 키를 복사하여 환경변수에 설정

**주의사항:**
- API 키는 비공개로 유지하세요
- 사용량에 따라 비용이 발생할 수 있습니다
- API 키가 노출되면 즉시 재발급하세요

## 📁 프로젝트 구조

```
naver-blog-automation/
├── main_streamlit.py          # 메인 Streamlit 애플리케이션
├── requirements.txt           # Python 의존성
├── pyproject.toml            # 프로젝트 설정
├── .gitignore               # Git 무시 파일
├── env.example              # 환경변수 예시 파일
├── README.md                # 프로젝트 문서
├── data/                    # 데이터 관리 모듈
│   ├── parsing_data.py
│   ├── content_data.py
│   └── ...
├── web/                     # 웹 자동화 모듈
│   ├── webdriver.py
│   ├── login.py
│   └── ...
├── task/                    # 작업 실행 모듈
│   ├── automator.py
│   └── ...
└── ui/                      # UI 관련 모듈
    ├── window.py
    └── ...
```

## 🔧 사용 방법

### 1. API 설정
- 환경변수에서 자동으로 API 키를 로드하거나
- UI에서 직접 API 키를 입력하고 인증

### 2. 계정 데이터 추가
- 네이버 아이디, 비밀번호, 장소 정보 입력
- 여러 계정을 등록하여 순차 포스팅 가능

### 3. 프롬프트 관리
- 재사용 가능한 프롬프트 템플릿 등록
- 프롬프트 미리보기 기능

### 4. 이미지 폴더 등록
- 포스팅에 사용할 이미지가 있는 폴더 선택
- 이미지 미리보기 및 관리

### 5. 작업 수행
- 설정된 계정으로 자동 로그인
- AI가 생성한 콘텐츠로 자동 포스팅

## 🛡️ 보안 주의사항

- **절대 `.env` 파일을 Git에 커밋하지 마세요**
- API 키는 환경변수로만 관리하세요
- 프로덕션 환경에서는 강력한 비밀번호를 사용하세요
- 정기적으로 API 키를 갱신하세요

## 🐛 문제 해결

### Chrome 드라이버 오류
- Chrome 브라우저가 최신 버전인지 확인
- `webdriver-manager`가 자동으로 드라이버를 다운로드합니다

### API 인증 실패
- API 키가 올바른지 확인
- API 키에 필요한 권한이 있는지 확인
- 네트워크 연결 상태 확인

### 로그인 실패
- 네이버 계정 정보가 올바른지 확인
- 2단계 인증이 설정되어 있는지 확인
- 캡챠가 발생한 경우 수동으로 해결

## 🤝 기여하기

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📄 라이선스

이 프로젝트는 MIT 라이선스 하에 배포됩니다. 자세한 내용은 `LICENSE` 파일을 참조하세요.

## 📞 지원

문제가 발생하거나 질문이 있으시면 [Issues](https://github.com/yourusername/naver-blog-automation/issues)에 등록해주세요.

## ⚠️ 면책 조항

이 도구는 교육 및 연구 목적으로만 사용되어야 합니다. 네이버의 이용약관을 준수하여 사용하시기 바랍니다. 사용자가 발생시킨 모든 문제에 대해 개발자는 책임지지 않습니다.