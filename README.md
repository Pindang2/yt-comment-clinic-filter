# yt-comment-clinic-filter
A filter for YT Comment Clinic Extension

YT Comment Clinic을 위한 필터.

---
## API 사용법

### 1. 필터 목록 불러오기 (filterlist.json)

모든 필터 목록을 불러오려면 다음 URL을 사용하세요:
```
https://cdn.jsdelivr.net/gh/Pindang2/yt-comment-clinic-filter@main/filterlist.json
```

filterlist.json 형식:
```json
{
    "TOC": ["Korean"],
    "Korean": {
        "rel": 1.0,
        "relver": "0002",
        "is_beta": true,
        "description": "한국어 기본 필터"
    }
}
```

- `TOC`: 사용 가능한 모든 필터 이름 목록
- 각 필터에는 다음 정보가 포함됩니다:
  - `rel`: 릴리스 버전
  - `relver`: 버전 번호
  - `is_beta`: 베타 여부
  - `description`: 필터 설명


### 2. 개별 필터 직접 액세스

각 필터는 다음 URL 패턴으로 직접 액세스할 수 있습니다:
```
https://cdn.jsdelivr.net/gh/Pindang2/yt-comment-clinic-filter@main/Filters/<필터이름>.json
```

예시 (Korean.json):
```
https://cdn.jsdelivr.net/gh/Pindang2/yt-comment-clinic-filter@main/Filters/Korean.json
```

Korean.json 형식:
```json
{
    "lang": "ko-KR",
    "version": "b0.1 v0002",
    "beta": true,
    "description": "한국어 기본 필터",
    "filters": [
        {
            "type": "accountpattern",
            "template": "^@(?:Top_)?([Il])_9_(?:쳬널|금).+쳬널.+$"
        },
        // 기타 필터 규칙...
    ]
}
```
filters의 type은 다음과 같이 나뉩니다:
- `accountpattern`: 계정 패턴 필터 (특정 패턴을 가지는 계정을 차단하기 좋음)
- `account`: 특정 계정 필터 (안중근 사진이랑 이름 걸어놓고 더러운 소리하는 개씹씹씹씹새끼같은 놈 차단하려고 만든 타입)
<sub>근데 막상 필터를 만들려고 보니 걔가 안보임 어디갔어 제보좀 부탁드립니다</sub>**찾았다!!!!**
- `pattern`: 패턴 필터 (패턴 하나로 여러 상황에 유연하게 적용 가능)
- `string`: 문자열 필터 (완벽히 일치하는 문자열만을 차단하기 좋음)
- `word`: 단어 필터 (일치하는 단어 단위로 차단하기 좋음)





## 업데이트 정보
- 필터 목록이 업데이트되면 jsDelivr는 자동으로 캐시를 갱신합니다(보통 24시간 이내).
- 최신 업데이트를 확인하려면 GitHub 저장소를 방문하세요: 
  [https://github.com/Pindang2/yt-comment-clinic-filter](https://github.com/Pindang2/yt-comment-clinic-filter)

