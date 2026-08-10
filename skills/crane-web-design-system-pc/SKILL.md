---
name: crane-web-design-system-pc
description: "두루미(crane)의 표준 웹(PC) 디자인 시스템이 작성되어 있는 SKILL입니다. 사용자가 두루미의 웹(PC) 디자인 작업을 요청하는 상황에 사용합니다. 이 SKILL은 PC 기준으로 작성되었습니다. 주의해 주세요."
---

# 두루미 웹디자인 시스템(PC)


## 필법(筆法)
서체(書體): KoPubWorld 바탕체
현판(懸板): 40px/1.2/700/-0.05em
주련(柱聯): 32px/1.3/500/-0.04em
화제(畵題): 24px/1.4/500/-0.03em
소해(小楷): 18px/1.6/300/-0.03em + 18px/1.6/500/-0.03em
관지(款識): 14px/1.5/300/-0.02em + 14px/1.5/500/-0.02em


## 묵법(墨法)


### 지(紙)
옥판선지(玉版宣紙): oklch(1.000 0.000 95) #FFFFFF
화선지(畵宣紙): oklch(0.995 0.004 95) #FEFDFA
장지(壯紙): oklch(0.960 0.008 95) #F3F2EC


### 묵(墨)
담묵(淡墨): oklch(0.800 0.003 245) #BCBEBF
중묵(中墨): oklch(0.500 0.006 245) #606466
농묵(濃墨): oklch(0.200 0.012 245) #12171B


### 주(朱)
인주(印朱): oklch(0.530 0.207 22.3) #C8102E


## 포백(布白)
계백당흑(計白當黑): 여백이 만드는 고급스러움을 압니다.
소밀(疏密): 밀도의 대비를 활용하여 직관적으로 전달합니다.
결구(結構): 8px의 배수
행기(行氣): 160px의 배수
장법(章法): 1080px


## 방원(方圓)
원만(圓滿): superellipse(2.5)
반경(半徑): 24px의 배수


## 서간(書簡)
높이: 48px
배경: 화선지(畵宣紙)
윤곽: 담묵(淡墨) 1px
글: 소해(小楷)
빈 글: 담묵(淡墨)
쓴 글: 농묵(濃墨)


## 창호(窓戶)
막: 지(紙) / 0.800
비침: backdrop-filter blur(8px) saturate(0.800)
결: feTurbulence fractalNoise. baseFrequency 1 0.5, numOctaves 1, seed 10, stitchTiles stitch
얹기: 결 saturate(0) multiply(0.100)


## 호응(呼應)
윤(潤): hover. 화선지(畵宣紙) → 옥판선지(玉版宣紙). 담묵(淡墨) → 중묵(中墨). 중묵(中墨) → 농묵(濃墨). 농묵(濃墨) → 인주(印朱).
점정(點睛): focus. 윤곽을 인주(印朱)로 강조합니다.


## 범례(凡例)
필법(筆法): 코드 작성 시 폰트 크기를 rem으로 작성해야 함.
방원(方圓): 반경이 0이면 corner-shape가 안 먹으니 반경부터 넣어야 함. 미지원 브라우저는 알아서 둥근 모서리로 보여주므로 그대로 두면 됨.
창호(窓戶): 막은 지(紙)의 알파로 구현해야 함. 요소 opacity를 쓰면 안의 글까지 옅어짐.
창호(窓戶): 사파리가 아직 -webkit-을 원하니 backdrop-filter는 접두사와 같이 적어야 함.
창호(窓戶): 결은 ::after로 올리고 border-radius와 corner-shape를 inherit로 받아 방원(方圓)을 따라가게 해야 함. 창호에 isolation: isolate를 걸어야 곱하기가 밖으로 안 샘.
호응(呼應): 윤(潤)에서 농묵(濃墨) → 인주(印朱)는 결정적인 곳에만 사용해야 함.
호응(呼應): 점정(點睛)은 :focus 말고 :focus-visible에 걸어야 함. 서간은 글 쓰는 칸이라 눌러 들어가도 알아서 찍힘.


## 파일
templates/fonts/: 서체 실파일. 웹 프로젝트에 폴더째 복사하고 fonts.css를 링크해 쓴다
templates/fonts/fonts.css: @font-face 세 벌 — 300·500·700
templates/fonts/KoPubWorld-Batang-Light.woff2: 300
templates/fonts/KoPubWorld-Batang-Medium.woff2: 500
templates/fonts/KoPubWorld-Batang-Bold.woff2: 700
templates/fonts/LICENSE.md: KoPubWorld 라이선스. 서체를 담아 배포할 때 함께 담는다
