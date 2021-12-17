---
title: Microsoft 生産性スコア
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
description: Microsoft 生産性スコアには、ユーザーやテクノロジのエクスペリエンス測定がどのように反映されているか、同規模の組織との比較をご覧ください。
ms.openlocfilehash: be8715942639b3e00fc3a8d49782684bbef99fbf
ms.sourcegitcommit: 6dcc3b039e0f0b9bae17c386f14ed2b577b453a6
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/15/2021
ms.locfileid: "61530849"
---
# <a name="microsoft-productivity-score"></a>Microsoft 生産性スコア 

生産性スコアは、組織での Microsoft 365 の使用方法に関する分析情報とそれをサポートする技術エクスペリエンスを提供することで、デジタル変革の行程をサポートします。 組織のスコアはユーザーと技術エクスペリエンスの測定を反映しており、同様の規模の別の組織によるベンチマークと比較できます。

次の情報を提供しています。

- **指標**: デジタル変革の行程のどの段階にあるかを知るのに役立ちます。
- **分析情報**: 組織の生産性と満足度を向上させる機会を特定するのに役立つデータについてのスコアです。
- **推奨アクション**: 組織が Microsoft 365 製品を効率的に使用できるように支援することができます。

次の 2 つの領域で、指標、分析情報、提案を提供します。 

- **ユーザー エクスペリエンス**: コンテンツの共同作業、モビリティ、コミュニケーション、会議、チームワークなどの Microsoft 365 のカテゴリを組織が仕事でどのように使用しているかを定量化します。  

    これらの各カテゴリについて公的研究を参照し、組織の効率性におけるベスト プラクティスと関連する特徴を特定します。 たとえば、Forrester のリサーチによると、ユーザーが共同作業をして (メール添付ではなく) クラウド上でコンテンツを共有するとき、1 週間あたり最大 100 分を削減できます。 さらに、Microsoft では組織内のこれらのベスト プラクティスの使用を定量化して、デジタル変革の行程のどの段階にあるかを知ることができるようサポートしています。 

- **テクノロジ エクスペリエンス**: 組織は、信頼性が高くパフォーマンスの高いテクノロジと、Microsoft 365 の効率的な使用に大きく左右されます。 [エンドポイント分析](https://aka.ms/endpointanalytics): ハードウェアとソフトウェアのパフォーマンスと正常性の問題が組織にどのように影響するかを理解するのに役立ちます。 Microsoft 365 アプリの正常性は、組織内のデバイスが推奨されているチャネルで Microsoft 365 アプリを実行しているかどうかを知るのに役立ちます。

## <a name="before-you-begin"></a>始める前に

概要と前提条件の詳細については、「[エンドポイント分析とは](/mem/analytics/overview)」を参照してください。 Microsoft 365 ネットワーク接続のインサイトの詳細については、「[ネットワーク接続の概要](../../enterprise/microsoft-365-networking-overview.md)」をお読みください。

ユーザーがデータを体験するには、Microsoft 365 for Business または Office 365 for enterprise サブスクリプションが必要です。 テナントのエンドポイント分析データについては、サブスクリプションに Microsoft Intune を追加する必要があります。 Intune を使用してデバイスとアプリを管理することで、組織のデータを保護できます。 Intune を入手したら、Intune エクスペリエンス内でエンドポイント分析を有効にできます。 Microsoft Intune の詳細については、「[Microsoft Intune documentation](/mem/intune/)」 を参照してください。 

> [!NOTE]
> 生産性スコア機能を取得するために、Workplace Analytics のライセンスは必要ありません。

生産性スコアは Microsoft 365 管理センターでのみ確認でき、次の役割のいずれかを持つ IT 担当者だけがアクセスできます:  

- グローバル管理者
- Exchange 管理者
- SharePoint 管理者
- Skype for Business 管理者
- Teams 管理者
- グローバル閲覧者
- レポート閲覧者
- 使用状況の概要レポート閲覧者

> [!NOTE]
> 生産性スコアにサインアップまたはテナントを選択できるのは、グローバル管理者の役割を持つ IT プロフェッショナルのみです。

生産性スコアのロールベースのアクセス制御のモデルは、組織内の IT 担当に柔軟な役割の割り当てを提供することで、組織の Microsoft 365 を使用したさらなるデジタル変革の道のりをサポートします。

Microsoft は、個人のプライバシーの保護に取り組んでいます。この「[プライバシーに関するドキュメント](privacy.md)」では、組織の IT 管理者に Microsoft が提供するコントロールについて説明します。これにより、Microsoft の信頼を損なうことなく、情報が実行可能であることを確認できます。

Microsoft 365 管理ホームの **[レポート]** > **[生産性スコア]** からエクスペリエンスにアクセスできます。
  
## <a name="how-the-score-is-calculated"></a>スコアの計算方法

生産性スコアは、ユーザー エクスペリエンスおよびテクノロジ エクスペリエンスのカテゴリを組み合わせたスコアに基づいています。 各カテゴリの比率は同じで、合計 100 ポイントです。 生産性スコアの最高得点は 800 です。

### <a name="score-categories"></a>スコア カテゴリ 

- コミュニケーション (100 ポイント)
- 会議 (100 ポイント)
- コンテンツの共同作業 (100 ポイント)
- チームワーク (100 ポイント)
- モビリティ (100 ポイント)
- エンドポイントの分析 (100 ポイント)
- ネットワーク接続 (100 ポイント)
- Microsoft 365 アプリの正常性 (100 ポイント)
- **最高合計得点 = 800 ポイント**
 
各スコア カテゴリで、組織がデジタル変革への過程において Microsoft 365 をどのように使用しているかに関するキー インジケーターを定量化します。 主要な活動の 28 日と 180 日のビューを提供します。 また、スコア計算には含まれないものの、対処すべき基本的な使用状況の統計や構成を特定するのに役立つ重要な指標も提供します。

### <a name="products-included-in-productivity-score"></a>生産性スコアに含まれる製品 

生産性スコアには、Exchange、SharePoint、OneDrive、Teams、Word、Excel、PowerPoint、OneNote、Outlook、Yammer、および Skype のデータが含まれます。

組織のスコアは毎日更新され、過去 28 日 (当日を含む) に完了したユーザーの操作を反映します。

## <a name="interpreting-your-organizations-productivity-score"></a>組織の生産性スコアを解釈する 

[生産性スコア] のホームページには、組織の合計スコアとスコア履歴、および各カテゴリの主要なインサイトが表示されます。

:::image type="content" source="../../media/prodscore-landing.png" alt-text="レポートの生産性スコアページ。":::

**組織のスコア** は、パーセント値とポイントで表示されます。 分子でポイントを、分母で取得可能な最大ポイントを確認できます。

**ピア ベンチマーク** を使用すると、組織のスコアを類似する別の組織と比較できます。 ユーザー エクスペリエンス カテゴリのピア ベンチマークは、同様の組織のセットでの平均測定値として計算されます。 組織のセットは、同様のライセンス ユーザー、ライセンスの種類、業界、Microsoft 365 の保有期間を持つ、同じ地域に位置する組織で構成されています。

> [!NOTE]
> Microsoft では、内部データを使用して、組織のマップ先の業界を決定します。 親組織のテナントは、親組織と同じ業界にマップされます。 組織は業界のマッピングを表示または変更できません。

エンドポイント分析ピア ベンチマークには、デバイスの起動パフォーマンスの目標と、すべてのテナントから集計された中央値に基づく推奨ソフトウェア構成が含まれます。

ネットワーク接続の場合、推奨されるベンチマークは 80 ポイントです。

**スコアの内訳** セクションでは、生産性スコアの内訳と、人およびテクノロジ エクスペリエンスの分野ごとのベンチマークを提供します。

スコア履歴には、過去 6 か月間の各カテゴリのスコアの変化が表示されます。

**ユーザー エクスペリエンス** と **テクノロジ エクスペリエンス** の領域には、これらの領域のカテゴリに関する主要な分析情報が含まれています。 各カテゴリを選択すると、さらに詳細な分析情報が表示されます。

## <a name="category-details-pages"></a>カテゴリ詳細ページ

各カテゴリの詳細ページには、主要な分析情報とサポート指標、および組織の変化を促進するために実行できる、関連する調査とアクションが表示されます。 リサーチは、各カテゴリの主要な分析情報の背後にある重要性と理論的根拠をサポートしています。 詳細については、[Forrester のレポート](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE2PBrb)を参照してください。

詳細ページは次の通りです。
- [コンテンツの共同作業 – ユーザー エクスペリエンス](content-collaboration.md)
- [コミュニケーション – ユーザー エクスペリエンス](communication.md)
- [会議 – ユーザー エクスペリエンス](meetings.md)
- [モビリティ – ユーザー エクスペリエンス](mobility.md)
- [チームワーク – ユーザー エクスペリエンス](teamwork.md)
- [Microsoft 365 アプリの正常性 – テクノロジ エクスペリエンス](apps-health.md)
- [エンドポイントの分析](/mem/analytics/productivity-score)

## <a name="business-continuity-special-report"></a>ビジネス継続性特別レポート

ビジネス継続性レポートは、Microsoft 365 のすべてのお客様が利用できる期間限定のワークプレイス インテリジェンス レポートであり、この困難な時期に組織をガイドするのに役立ちます。  

このレポートは組織が次のことを理解するのに役立ちます: 

- リモート ワークへの移行がコラボレーションとコミュニケーションに与える影響。 

- 在宅勤務に適応することによるワーク ライフ バランスへの影響。 

- リモート会議が効果的な意思決定をサポートしているかどうか。

[ビジネス継続性レポートの詳細情報](/Workplace-Analytics/tutorials/bcrps)

[Microsoft Graph の詳細情報](/graph/)

> [!NOTE]
> また、ユーザーは、 [MyAnalytics ダッシュボード](/workplace-analytics/myanalytics/use/dashboard-2)から生産性に関する分析情報を得ることもできます。


## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

生産性スコアについての考えと、改善方法についてのアイデアをお聞かせください。 製品内の **フィードバック** セクションを使用するか、生産性スコア チーム prodscorefeedback@microsoft.com までご連絡ください。

## <a name="related-content"></a>関連コンテンツ

[レポートを使用して Microsoft 365 のアクティビティを監視する](../../admin/activity-reports/activity-reports.md) (記事)\
[Microsoft 365 利用状況分析を有効にする](../../admin/usage-analytics/enable-usage-analytics.md) (記事)\
[Microsoft 365 管理センターの概要](Microsoft 365 管理センターの概要](../admin-overview/admin-center-overview.md) (ビデオ)