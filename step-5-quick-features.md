# STEP 5. Quick 차별 기능

> Quick만의 4가지 차별 기능을 훑어봅니다. Scheduled Agent · Apps · Knowledge Graph · Browser.

---

## 5-1. Scheduled Agent

정해진 시간에 자동으로 도는 에이전트를 만듭니다.

```
매일 아침 8시에 내 이메일을 요약해서 알려주는 에이전트를 만들어줘.
```

→ 승인하면 생성 + 즉시 테스트 실행. 결과는 오른쪽 위 **Activity Feed** 에 표시됩니다.

> **주의:** 이메일 Connection이 필요합니다. (STEP 4에서 연결)

변형:

```
회의 30분 전에, 내가 준비 안 한 미팅이 있으면 알려주는 에이전트를 만들어줘.
```

---

## 5-2. Apps (대시보드)

Quick 안에서 쓰는 앱을 만듭니다. STEP 3의 HTML 대시보드와 달리 Quick 내부에서 실행됩니다.

```
./customer-usage.csv 데이터로 고객 사용량 대시보드 앱을 만들어줘. 고객사별 API 호출수, 세그먼트별 분포, 상위 고객사를 한눈에 볼 수 있게 해줘.
```

---

## 5-3. Knowledge Graph

Quick이 축적한 내 컨텍스트(계정·사람·조직 관계)를 시각적으로 확인합니다.

**1.** **Settings**(왼쪽 아래 톱니) **→ My Context → Knowledge Graph** 를 엽니다.

**2.** 노드/관계를 확인합니다.

**3.** 채팅으로도 물어볼 수 있습니다.

```
내 Knowledge Graph 보여줘
```

또는

```
Quick이 [계정/사람]에 대해 뭘 알고 있어?
```

---

## 5-4. Browser (진짜 웹에서 찾아오기)

**셋업:**

**Settings → Customization → Browser** → 브라우저 선택(Chrome 등) → **"Use my browser"** 토글 ON → 안내대로 `chrome://inspect/#remote-debugging` 붙여넣고 **Enable remote debugging** → **Test Connection** → "Connected" 확인.

<figure><img src="images/quick-browser-customization.png" alt="브라우저 커스터마이징"><figcaption>브라우저 커스터마이징</figcaption></figure>

**써보기:**

```
쿠팡에서 "무선 키보드" 검색 결과 페이지를 열어서, 상위 5개 상품의 이름·가격·별점을 표로 정리해줘.
```

→ Quick이 실제로 브라우저를 열어 페이지를 읽어옵니다. 내 로그인/쿠키 그대로 사용됩니다.

> **팁:** 검색(네이버 등)은 사이트가 막아서 잘 안 될 수 있어요. 쿠팡 검색이 막히면 상품 **URL을 직접** 주고 "이 상품 리뷰 요약해줘"로 하는 게 확실합니다.

---

> **다음:** [STEP 6. 최종 체크 →](step-6-checklist.md)
