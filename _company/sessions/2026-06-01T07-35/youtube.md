# 📺 레오 — 레오가 작성한 스크립트 초안을 바탕으로, 1 분 분량 유튜브 영상의 구체적인 촬영 브리프 (장비·배경·의상·조명) 와 편집 가이드라인 생성. 썸네일 배경색 (#E50914) 과 일치하는 비주얼 요소 강조.

⚠️ 레오 LLM 호출 실패: LLM 응답 중 60초 초과. 저사양 머신이면 settings.json에서 connectAiLab.streamFirstTokenTimeoutSec 값을 늘리거나 (예: 600), 더 작은 모델로 변경하세요 (gemma2:2b 1.6GB 등).

---

## 📊 LLM 실패에도 시스템이 가져온 실데이터는 보존됨



[실시간 데이터 — 시스템이 방금 도구로 가져온 진짜 출력]

### YouTube 채널 영상 분석 (실제 API 데이터) _(exit 1)_
```
Traceback (most recent call last):
  File "c:\Users\eunhw\.connect-ai-brain\_company\sessions\_company\_agents\youtube\tools\my_videos_check.py", line 478, in <module>
    main()
    ~~~~^^
  File "c:\Users\eunhw\.connect-ai-brain\_company\sessions\_company\_agents\youtube\tools\my_videos_check.py", line 135, in main
    print("\u274c YOUTUBE_API_KEY �̼���. youtube_account.json�� ä���ּ���.")
    ~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
UnicodeEncodeError: 'cp949' codec can't encode character '\u274c' in position 0: illegal multibyte sequence
```

### YouTube 설정 확인 (fallback) _(exit 1)_
```
������ YouTube ���� / ä�� ���� ������
  API Ű            : (�� ��)
  �� ä�� �ڵ�       : (����)
  �� ä�� ID        : (����)
  ���� ä�� (0��) : (����)
  ���� ä�� (0��): (����)
  �ڷ��׷�          : �̼��� (���� �˸� ��Ȱ��)
  Ollama URL        : http://127.0.0.1:11434
  �м� ��          : (�ڵ� ����)
Traceback (most recent call last):
  File "c:\Users\eunhw\.connect-ai-brain\_company\sessions\_company\_agents\youtube\tools\youtube_account.py", line 46, in <module>
    main()
    ~~~~^^
  File "c:\Users\eunhw\.connect-ai-brain\_company\sessions\_company\_agents\youtube\tools\youtube_account.py", line 40, in main
    print("\n\u26a0\ufe0f  API Ű�� ����־��. �ٸ� �������� �������� �ʽ��ϴ�.")
    ~~~~~^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
UnicodeEncodeError: 'cp949' codec can't encode character '\u26a0' in position 2: illegal multibyte sequence
```

🛑 **실시간 데이터 가져오기 실패** — 위 출력은 에러 메시지뿐. 사용자에게 정확히 무엇이 문제인지(Python 미설치? 패키지 미설치? API 키 미설정?) 알려주고, 가짜 분석·placeholder 데이터 절대 생성하지 마세요. 작업은 '대기' 평가로 끝내고 다음 단계는 사용자가 환경 셋업 후 재시도.

_위 데이터를 기반으로 다음 에이전트가 분석을 이어가야 합니다. "데이터 로드 실패"로 잘못 보고하지 마세요._
