[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18629367.svg)](https://doi.org/10.5281/zenodo.18629367)

Languages: [English](./README.md) · [Français](./readmeFR.md) · [한국어](./readmeKR.md) · [日本語](./readmeJP.md)


# dollarization-panel-data

# 글로벌 예금 달러라이제이션 패널 데이터셋 (1980–2019)

## 개요

**예금 달러라이제이션 비율**(외화예금 / 총예금)에 대한 패널 데이터셋으로, **1980년부터 2019년까지** **128개국**을 포괄하며, **2,646개 관측치**를 포함합니다. 데이터는 각국 중앙은행 간행물, IMF 스태프 리포트, CEIC에서 수집되었습니다.

이 데이터셋은 다음 석사 학위 논문의 일부로 구축되었습니다.

> **Jang, H. (2021). "Dollarization: Trends and its Determinants." Master’s Thesis, Graduate School of Commerce, Waseda University. Advisor: Prof. Koichi Takase.**

## 인용

이 데이터셋을 사용할 경우, 아래와 같이 인용해 주세요.

```
Jang, Hyungju (2021). Dollarization: Trends and its Determinants.
Master's Thesis, Waseda University. Dataset available at: [DOI]
```

## 파일

| 파일 | 설명 |
| --- | --- |
| `dollarization_panel.csv` | 정리된(tidy) 형식의 주요 패널 데이터셋 |
| `dollarization_sources.csv` | 국가별 중앙은행 데이터 소스 URL |
| `Data_dolrat_raw.xlsx` | 원시(raw) 데이터 파일 |

## 변수 정의

### dollarization_panel.csv

| 변수 | 설명 |
| --- | --- |
| `country` | 국가명 |
| `iso3` | ISO 3166-1 알파-3 국가 코드 |
| `year` | 연도 (1980–2019) |
| `fcd_td_ratio` | 예금 달러라이제이션 비율: 외화예금 ÷ 총예금 |

### dollarization_sources.csv

| 변수 | 설명 |
| --- | --- |
| `country` | 국가명 |
| `iso3` | ISO 3166-1 알파-3 국가 코드 |
| `source_url` | 중앙은행 또는 데이터 소스의 URL |

## 방법론

### 정의

달러라이제이션 비율은 다음과 같이 정의됩니다.

달러라이제이션 비율 = 외화예금(Foreign Currency Deposits, FCD) ÷ 총예금(Total Deposits, TD)

Mwase and Kumah (2015)를 따라, 분모로 광의통화(Broad Money)가 아니라 총예금(Total Deposits)을 사용합니다. 이는 Baliño et al. (1999)의 구(舊) 관행과 대비되며, 거주자가 예금을 외화로 보유하는 선호를 보다 정확히 포착하기 위한 선택입니다.

비율이 **30%**를 초과하는 국가는 **고도 달러화 경제(Highly Dollarized Economies, HDE)**로, **10–30%** 구간에 있는 국가는 **중간 수준 달러화 경제(Moderately Dollarized Economies, MDE)**로 분류합니다.

### 데이터 구성

- 1차 자료: 중앙은행 통계 게시물, 연차보고서, 데이터베이스
- 2차 자료: IMF 스태프 리포트, CEIC(중국의 경우)
- 일부 국가의 2000년 이전 역사 자료: Baliño et al. (1999)
- 보고 기준의 불일치를 피하기 위해, 각 국가는 가능하면 단일 소스에서 일관되게 자료를 수집했습니다.

### 커버리지

- 최소 한 개의 관측치를 가진 **128개국**
- 시계열 커버리지는 국가별로 상이함(자세한 내용은 논문 부록 참조)
- 대부분의 국가는 **2000년 이후** 자료를 가지며, 일부 국가는 **1980년**까지 소급됩니다.
- 커버리지는 시간에 따라 확대되며, 1980년 4개국 → 2014년 125개국까지 증가합니다.

## 유의 사항

### 완전 달러화 경제(데이터셋에 포함되지 않음)

다음 국가는 외국 통화를 법정통화로 채택했기 때문에, 예금 달러라이제이션 비율을 적용하기 어려워 **데이터셋에서 제외**됩니다.

| 국가 | 통화 | 채택 연도 |
| --- | --- | --- |
| 파나마 | 미국 달러(USD) | 1904 |
| 에콰도르 | USD | 2000 |
| 엘살바도르 | USD | 2001 |
| 짐바브웨 | 다수 통화 | 2009 |

추가로, CFA 프랑 지대 국가들(WAEMU/CEMAC)과 유로존 회원국은 형식적으로 달러화(외화화)된 경제로 간주합니다. 일부 유로존 가입 국가는 유로 도입 시점에 예금 달러라이제이션 비율이 급격히 하락하는데, 이는 에스토니아(2011), 라트비아(2014), 리투아니아(2015)와 같은 사례에서 관찰됩니다.

### 유로 효과

유로를 도입한 국가들은 도입 시점에 구조적 단절(structural break)을 보입니다. 유로 표시 예금이 외화예금에서 국내예금으로 재분류되기 때문입니다. 이에 따라 유럽 및 중앙아시아 지역 평균을 해석할 때는 이 점을 염두에 두어야 합니다.

### 알려진 한계

- 일부 국가는 FCD/총예금이 아니라 FCD/광의통화 비율만 보고합니다.
- 베네수엘라의 2019년 이전 비율은 통계 왜곡 가능성으로 인해 실제 달러라이제이션 수준을 반영하지 않을 수 있습니다.
- 일부 국가는 언어 장벽(예: 모리타니아)으로 인해 자료 수집이 제약되었습니다.
- 현금 형태의 외화 사용(지급 달러라이제이션, payment dollarization)은 이 지표에 포착되지 않습니다.
- 몇몇 고소득국(호주, 프랑스, 이탈리아, 아일랜드, 포르투갈, 뉴질랜드)은 거주자 외화예금 통계를 보고하지 않습니다.

## 데이터 품질 플래그

다음 경우에는 해석에 주의를 기울여야 합니다.

- **1995년 이전 데이터**: 40개 미만의 국가로 제한됨
- **이란**: 일부 소스에서 회계연도와 역년(calendar year)의 불일치
- **아르헨티나**: 여러 시기에 걸친 외화예금 규제 조치로 인해 보고된 비율에 왜곡 가능성
- **베네수엘라**: 데이터 신뢰성 문제(자세한 내용은 논문 2.3.2절 참조)

## 라이선스

이 데이터셋은 MIT 라이선스 하에 배포됩니다.  
적절한 출처 표기를 전제로 자유롭게 공유·수정할 수 있습니다.

전체 라이선스 내용은 [MIT License](https://opensource.org/licenses/MIT)를 참조하세요.

## 관련 문헌

- Baliño, T., Bennett, A., & Borensztein, E. (1999). "Monetary Policy in Dollarized Economies." IMF Occasional Paper 171.
- Levy-Yeyati, E. (2006). "Financial Dollarization: Evaluating its Consequences." *Economic Policy*, 21(45), 61–118.
- Mwase, N. & Kumah, Y. (2015). "Revisiting the Concept of Dollarization." IMF Working Paper WP/15/12.

## 연락처

Hyungju Jang — hyungju.jang@umontreal.ca  
https://github.com/hj8779