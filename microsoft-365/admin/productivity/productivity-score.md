---
title: Microsoft プロダクティビティスコア
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
monikerRange: o365-worldwide
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
description: Microsoft 生産性スコアの概要。
ms.openlocfilehash: f1edc1a66763562b233455609f3381e3f4fbfa98
ms.sourcegitcommit: 4debeb8f0fce67f361676340fc390f1b283a3069
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/03/2020
ms.locfileid: "49561480"
---
# <a name="microsoft-productivity-score"></a>Microsoft プロダクティビティスコア 

生産性スコアは、組織が Microsoft 365 とそれをサポートするテクノロジエクスペリエンスについての洞察による、デジタル変換への移行をサポートしています。 組織のスコアは、人と技術実績の測定基準を反映しており、サイズが自分のものと同じである組織のベンチマークと比較できます。

次の機能が提供されます。

- デジタル変換の過程にある場所を確認するのに役立つ **指標**。
- 組織での生産性と満足度を向上させる機会を特定するのに役立つデータに関する **洞察**。
- 組織が Microsoft 365 製品を効率的に使用できるようにするために **推奨される処置**。

次の2つの分野で、測定基準、洞察、および推奨事項を提供します。 

- **ユーザーエクスペリエンス:** コンテンツコラボレーション、モビリティ、コミュニケーション、会議、チームワークなどの Microsoft 365 カテゴリを使用して組織がどのように機能するかを Quantifies します。  

    記載されている各カテゴリについては、「公共の調査」を参照して、組織の有効性の形式に関するベストプラクティスと関連する利点を特定します。 たとえば、[Forrester] ( https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf 電子メールを送信するのではなく、クラウド内のコンテンツをグループ作業して共有している場合)、1週間に最大100分の時間を節約できることが、研究から示されています。 さらに、お客様の組織でこれらのベストプラクティスを使用することによって、デジタル変換の過程を確認できるようにしています。 

- **テクノロジエクスペリエンス:** 組織は、信頼性と優れたパフォーマンスを備えたテクノロジに加えて、Microsoft 365 の効率的な使用に依存しています。 [エンドポイント分析](https://aka.ms/endpointanalytics) は、ハードウェアおよびソフトウェアのパフォーマンスと正常性の問題によって組織が受ける影響を理解するのに役に立ちます。 Microsoft 365 アプリの正常性は、組織内のデバイスが推奨チャネルで Microsoft 365 アプリを実行しているかどうかを理解するのに役に立ちます。

概要と前提条件の詳細については、「 [エンドポイント分析とは](https://docs.microsoft.com/mem/analytics/overview) 」を参照してください。 Microsoft 365 network connectivity insights の詳細については、「 [ネットワーク接続の概要」](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-networking-overview)を参照してください。
  

## <a name="how-the-score-is-calculated"></a>スコアの計算方法

生産性スコアは、ユーザーとテクノロジエクスペリエンスのカテゴリの組み合わせに基づいています。 各カテゴリは均等に重み付けされ、合計100ポイントになります。 利用可能な最高の生産性スコアは800です。

### <a name="score-categories"></a>スコアカテゴリ 

- 通信 (100 ポイント)
- 会議 (100 ポイント)
- コンテンツコラボレーション (100 ポイント)
- チームワーク (100 ポイント)
- モビリティ (100 ポイント)
- エンドポイント分析 (100 ポイント)
- ネットワーク接続 (100 ポイント)
- Microsoft 365 アプリの正常性 (100 ポイント)
- **使用可能な合計 = 800 ポイント**
 
 各スコアカテゴリでは、組織がどのように Microsoft 365 を使用しているかを示す重要な指標が、デジタル変換への移行について数値化されています。 重要なアクティビティについては、28日と180日のビューが提供されています。 また、スコア計算の一部ではないサポート指標も提供していますが、対処可能な基になる利用状況の統計および構成を識別するのに役立ちます。

### <a name="products-included-in-productivity-score"></a>生産性スコアに含まれる製品 

生産性スコアには、Exchange、SharePoint、OneDrive、Teams、Word、Excel、PowerPoint、OneNote、Outlook、Yammer、Skype からのデータが含まれます。

組織のスコアは毎日更新され、最後の 28 (現在の日付を含む) で完了したユーザー操作を反映します。


## <a name="pre-requisites"></a>前提条件 

ユーザーがデータを体験できるようにするには、Microsoft 365 for business または Office 365 for enterprise のサブスクリプションが必要です。 テナントのエンドポイント分析データについては、サブスクリプションに Microsoft Intune を追加する必要があります。 Intune は、デバイスとアプリを管理することによって、組織のデータを保護することができます。 Intune を使用すると、Intune でエンドポイント分析を有効にすることができます。 [Microsoft Intune](https://docs.microsoft.com/mem/intune/)の詳細について説明します。 
> [!NOTE]
> 生産性スコア機能を取得するために、Workplace Analytics のライセンスは必要ありません。

生産性スコアは、Microsoft 365 管理センターでのみ利用可能であり、次のいずれかの役割を持つ IT 担当者のみがアクセスできます。  

- グローバル管理者 
- Exchange の管理者
- SharePoint 管理者 
- Skype for Business 管理者 
- Teams 管理者 
- グローバル閲覧者 
- レポート閲覧者 

この情報は、Microsoft 365 を使用した furthering デジタル変換にのみ使用することを目的としているため、裁量で共有する必要があります。 

Microsoft は個人のプライバシーの保護に取り組んでいます。 この [プライバシー](privacy.md)  に関するドキュメントでは、組織の IT 管理者として提供するコントロールについて説明します。これにより、Microsoft での信頼を侵害せずに、その情報を確実に利用できるようになります。

Microsoft 365 管理ホームから、[**レポート** の  >  **生産性スコア**] の下にある [experience] にアクセスできます。

## <a name="interpreting-your-organizations-productivity-score"></a>組織の生産性スコアを解釈する 

[プロダクティビティスコア] ホームページには、組織の総得点とスコアの履歴、および各カテゴリの主要な洞察が表示されます。

:::image type="content" source="../../media/prodscore-landing.png" alt-text="レポートの [生産性スコア] ページ":::

**組織のスコア** は、パーセント値とポイントで示されます。 分子にポイントと、分母に可能な最大ポイントが表示されます。

**ピアベンチマーク** を使用すると、組織のスコアを自分のような組織と比較できます。 People エクスペリエンスカテゴリのピアベンチマークは、類似した組織のセット内のメジャーの平均として計算されます。 この一連の組織は、ライセンスが付与されたユーザーの数、ライセンス、業界、365 tenure の種類がある、地域内の組織で構成されています。 

Endpoint analytics ピアベンチマークには、すべてのテナントでの集約された中央値に基づいた、デバイスの起動パフォーマンスおよび推奨されるソフトウェア構成のターゲットが含まれています。

ネットワーク接続の場合、推奨されるベンチマークは80ポイントです。

「 **Score 降伏** 」セクションでは、ユーザーとテクノロジの分野によるベンチマークを使用して、生産性スコアの内訳を示します。

スコア履歴では、各カテゴリのスコアが過去6か月にどのように変化したかが表示されます。

**ユーザーエクスペリエンス** と **テクノロジエクスペリエンス** の分野には、これらの分野のカテゴリの主要な情報が含まれています。 各カテゴリをクリックすると、さらに詳しい情報を参照できます。

## <a name="category-details-pages"></a>カテゴリ詳細ページ

各カテゴリ詳細ページには、主要な洞察とサポート指標のほか、組織内での変更を促進するために実行できる関連調査とアクションが表示されます。 調査では、各カテゴリの主要な洞察の背後にある重要事項と論理的根拠がサポートされています。 詳細については、 [Forrester レポートを参照して](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)ください。

詳細ページは次のとおりです。
- [コンテンツコラボレーション–ユーザーエクスペリエンス](content-collaboration.md)
- [コミュニケーション–ユーザーエクスペリエンス](communication.md)
- [会議–ユーザーエクスペリエンス](meetings.md)
- [モビリティ–ユーザーエクスペリエンス](mobility.md)
- [チームワーク–ユーザーエクスペリエンス](teamwork.md)
- [Microsoft 365 アプリの正常性–テクノロジエクスペリエンス](apps-health.md)

## <a name="business-continuity-special-report"></a>ビジネス継続性の特別なレポート

ビジネス継続性レポートは、Microsoft 365 のすべてのお客様が、このような問題が発生している間に組織をガイドするのに役立つ、限られたタイムワークプレースインテリジェンスレポートです。  

このレポートにより、組織は次のことを理解できます。 

- Shift キーを押したときのリモート処理によるコラボレーションと通信への影響 

- ユーザーが自宅から作業するために調整したときのワークライフバランスへの影響。 

- リモート会議が効果的な意思決定をサポートするかどうか。

[ビジネス継続性レポートの詳細情報](https://aka.ms/bcrps)

[Microsoft Graph の詳細情報](https://docs.microsoft.com/graph/)

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

生産性スコアに関する考えと、それを改善する方法についてのアイデアを共有します。 製品内の **フィードバック** セクションを使用して、Prodscorefeedback@microsoft.com の生産性スコアチームに連絡します。
