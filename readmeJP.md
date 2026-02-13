[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.18629367.svg)](https://doi.org/10.5281/zenodo.18629367)

Languages: [English](./README.md) · [Français](./readmeFR.md) · [한국어](./readmeKR.md) · [日本語](./readmeJP.md)

# dollarization-panel-data

# グローバル預金ドル化パネルデータセット（1980–2019）

## 概要

**預金ドル化比率**（外貨預金 / 総預金）に関するパネルデータセットであり、**1980年から2019年まで**の **128か国**を対象とし、**2,646件の観測値**を含みます。データは各国中央銀行の刊行物、IMFスタッフレポート、CEIC から収集されています。

本データセットは、以下の修士論文の一部として構築されました。

> **Jang, H. (2021). "Dollarization: Trends and its Determinants." Master’s Thesis, Graduate School of Commerce, Waseda University. Advisor: Prof. Koichi Takase.**

## 引用方法

このデータセットを利用する場合は、以下のように引用してください。

```
Jang, Hyungju (2021). Dollarization: Trends and its Determinants.
Master's Thesis, Waseda University. Dataset available at: [DOI]
```

## ファイル

| ファイル | 説明 |
| --- | --- |
| `dollarization_panel.csv` | 整形済み（tidy）形式のメインパネルデータセット |
| `dollarization_sources.csv` | 各国の中央銀行データソース URL |
| `Data_dolrat_raw.xlsx` | 元の生データ（raw data）ファイル |

## 変数の定義

### dollarization_panel.csv

| 変数 | 説明 |
| --- | --- |
| `country` | 国名 |
| `iso3` | ISO 3166-1 アルファ3国コード |
| `year` | 年（1980–2019） |
| `fcd_td_ratio` | 預金ドル化比率：外貨預金 ÷ 総預金 |

### dollarization_sources.csv

| 変数 | 説明 |
| --- | --- |
| `country` | 国名 |
| `iso3` | ISO 3166-1 アルファ3国コード |
| `source_url` | 中央銀行またはデータソースの URL |

## 方法論

### 定義

ドル化比率は、次のように定義されます。

ドル化比率 ＝ 外貨預金（Foreign Currency Deposits, FCD） ÷ 総預金（Total Deposits, TD）

Mwase and Kumah (2015) に従い、分母には従来の Baliño et al. (1999) の慣行で用いられていた広義流動性（Broad Money）ではなく、総預金（Total Deposits）を用いています。これにより、居住者が預金を外貨建てで保有する選好をより正確に捉えることを目指しています。

比率が **30％** を超える国は **高ドル化経済（Highly Dollarized Economies, HDE）**、**10–30％** の範囲にある国は **中程度ドル化経済（Moderately Dollarized Economies, MDE）** と分類されます。

### データ構築

- 一次情報源：中央銀行統計（統計公表物）、年次報告書、各種データベース
- 二次情報源：IMF スタッフレポート、CEIC（中国について）
- 一部の国の 2000 年以前の歴史データ：Baliño et al. (1999)
- 報告基準の不整合を避けるため、各国については可能な限り単一の情報源から一貫してデータを取得しています。

### カバレッジ

- 少なくとも 1 つの観測値を持つ **128か国**
- 時系列のカバレッジは国によって異なります（詳細は論文付録を参照）
- 多くの国は **2000年以降** のデータを有し、一部の国は **1980年** まで遡ります。
- カバレッジは時間とともに拡大しており、1980年の 4か国 から 2014年には 125か国 まで増加しています。

## 留意点

### 完全ドル化経済（データセットには未収録）

以下の国々は、外国通貨を法定通貨として採用しているため、預金ドル化比率を適用できず、**本データセットからは除外**されています。

| 国 | 通貨 | 採用年 |
| --- | --- | --- |
| パナマ | 米ドル（USD） | 1904 |
| エクアドル | USD | 2000 |
| エルサルバドル | USD | 2001 |
| ジンバブエ | 複数通貨 | 2009 |

さらに、CFA フラン圏諸国（WAEMU/CEMAC）およびユーロ圏加盟国は、形式的に「外貨建て経済」とみなされます。いくつかのユーロ導入国では、ユーロ採用時点で預金ドル化比率が急激に低下しており、エストニア（2011年）、ラトビア（2014年）、リトアニア（2015年）などがその例です。

### ユーロ導入の影響

ユーロを導入した国では、導入時点でドル化比率に**構造的な変化（structural break）**が生じます。ユーロ建て預金が「外貨預金」から「国内通貨建て預金」に再分類されるためです。そのため、ヨーロッパおよび中央アジア地域の平均値を解釈する際には、この点を考慮する必要があります。

### 既知の制約

- 一部の国は FCD/総預金 ではなく FCD/広義流動性 のみを公表しています。
- ベネズエラの 2019 年以前の比率は、統計上の不正確さが疑われており、実際のドル化水準を反映していない可能性があります。
- モーリタニアなど、一部の国では言語上の制約によりデータ収集が困難でした。
- 現金による外貨使用（決済ドル化・payment dollarization）は、この指標には反映されていません。
- いくつかの高所得国（オーストラリア、フランス、イタリア、アイルランド、ポルトガル、ニュージーランド）は、居住者外貨預金統計を公表していません。

## データ品質に関する注意

次のようなケースでは、解釈に際して特に注意が必要です。

- **1995年以前のデータ**：40か国未満に限られます。
- **イラン**：一部の情報源では会計年度と暦年（calendar year）が一致していません。
- **アルゼンチン**：複数の時期において外貨預金に対する規制措置が実施されており、報告値に歪みがある可能性があります。
- **ベネズエラ**：データの信頼性に問題があり、詳細は論文第 2.3.2 節を参照してください。

## ライセンス

本データセットは MIT ライセンスの下で公開されています。  
適切なクレジットを付すことを条件に、データの共有および改変が認められます。

ライセンス全文は [MIT License](https://opensource.org/licenses/MIT) を参照してください。

## 関連文献

- Baliño, T., Bennett, A., & Borensztein, E. (1999). "Monetary Policy in Dollarized Economies." IMF Occasional Paper 171.
- Levy-Yeyati, E. (2006). "Financial Dollarization: Evaluating its Consequences." *Economic Policy*, 21(45), 61–118.
- Mwase, N. & Kumah, Y. (2015). "Revisiting the Concept of Dollarization." IMF Working Paper WP/15/12.

## 連絡先

Hyungju Jang — hyungju.jang@umontreal.ca  
https://github.com/hj8779