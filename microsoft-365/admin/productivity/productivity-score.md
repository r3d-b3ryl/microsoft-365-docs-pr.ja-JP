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
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 生産性スコアの概要。
ms.openlocfilehash: 3d014cd0eb3a3ceed3b3f3b48f126453e4ced193
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/29/2020
ms.locfileid: "48794967"
---
# <a name="microsoft-productivity-score"></a>Microsoft プロダクティビティスコア 

生産性スコアは、ユーザーが Microsoft 365 を使用する方法と、それらをサポートするテクノロジエクスペリエンスについて、組織がどのように作業を遂行するかを分析するのに役立ちます。 スコアはユーザーやテクノロジエクスペリエンスに対する組織の業績を反映し、自分のスコアを自分のような組織と比較します。

スコアには次のものが含まれます。

- ユーザーがどのように Microsoft 365 製品を使用してプラットフォーム間でコラボレーション、コミュニケーション、作業を行っているかを確認するのに役立つ **指標** 。
- 従業員の生産性と満足度を向上させるチャンスを特定するのに役立つデータに関する **洞察** 。
- 組織内のユーザーが Microsoft 365 製品を効率的に使用できるようにするために推奨される **処置** 。すべてのユーザーが最善の作業を行うことができます。

データ、洞察、推奨事項は、次の2つの領域で提供されています。 

- **ユーザーエクスペリエンス:** ユーザーがコンテンツに対してどのようにコラボレーションするか、どのように Microsoft 365 製品を使用して通信するか、また複数のプラットフォームで Microsoft 365 を使用するかどうかを測定します。 

    このような洞察を提供しているのは、ユーザーがオンラインで作業するときに、時間を節約し、あらゆるデバイスで作業できるようにすることで、より生産的で満足度が高くなるためです。 柔軟な方法で通信できるため、より効率的に作業を行うことができ、組織がより統合されるようになります。 エビデンスについては、「 [Forrester report](https://vc2prod.blob.core.windows.net/vc-resources/TEIStudies/TEI%20of%20Microsoft%20365%20E5%20-%20Oct%202018.pdf)」を参照してください。

- **テクノロジエクスペリエンス:** 生産性を向上させるには、信頼性が高く、優れたパフォーマンスを持つテクノロジに加えて、Microsoft 365 を効率的に使用します。 [エンドポイント分析](https://aka.ms/endpointanalytics)を提供することで、エンドポイントのハードウェアとソフトウェアのパフォーマンスと正常性の問題によってユーザーの生産性がどのように影響されるかを理解するのに役立つ情報を提供します。 また、お客様の組織のために Microsoft 365 network connectivity insights に加えて、推奨される処置を行うこともできます。

概要と前提条件の詳細については、「 [エンドポイント分析とは](https://docs.microsoft.com/mem/analytics/overview) 」を参照してください。 Microsoft 365 network connectivity insights の詳細については、「 [ネットワーク接続の概要」](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-networking-overview)を参照してください。
  

## <a name="how-the-score-is-calculated"></a>スコアの計算方法

生産性スコアは、ユーザーとテクノロジエクスペリエンスのカテゴリの組み合わせに基づいています。 各カテゴリは均等に重み付けされ、合計100ポイントになります。 利用可能な最高の生産性スコアは500です。

### <a name="score-categories"></a>スコアカテゴリ 

- コンテンツコラボレーション (100 ポイント)
- 通信 (100 ポイント)
- モビリティ (100 ポイント)
- エンドポイント分析 (100 ポイント)
- ネットワーク接続 (100 ポイント)
- **使用可能な合計 = 500 ポイント**
 
 各カテゴリでは、ユーザーがどのように Microsoft 365 製品を使用してプラットフォーム間でコラボレーション、コミュニケーション、作業を行うかを示す指標となる主要なアクティビティのパターンを特定します。 重要なアクティビティについては、28日と180日のビューが提供されています。 また、スコア計算の一部ではないサポート指標も提供していますが、対象となる動作と設定を特定するのに役立ちます。

### <a name="products-included-in-productivity-score"></a>生産性スコアに含まれる製品 

生産性スコアには、Exchange、SharePoint、OneDrive、Teams、Word、Excel、PowerPoint、OneNote、Outlook、Yammer、Skype からのデータが含まれます。

スコアは毎日更新され、最後の 28 (現在の日付を含む) で完了したユーザー操作を反映します。


## <a name="pre-requisites"></a>前提条件 

ユーザーエクスペリエンスデータを取得するには、Microsoft 365 for business または Office 365 for enterprise サブスクリプションが必要で、マルチテナントクラウドサービスを使用する必要があります。 テナントのエンドポイント分析データを取得するには、サブスクリプションに Microsoft Intune を追加する必要があります。 Intune は、デバイスとアプリを管理することによって、組織のデータを保護することができます。       Intune を使用すると、Intune でエンドポイント分析を有効にすることができます。 Microsoft Intune の詳細について説明します。 

組織の生産性スコアを表示するには、次のいずれかの役割を持っている必要があります。 

- グローバル管理者 
- Exchange の管理者
- SharePoint 管理者 
- Skype for Business 管理者 
- Teams 管理者 
- グローバル閲覧者 
- レポート閲覧者 

Microsoft 365 管理ホームから、[ **レポート** の  >  **生産性スコア** ] の下にある [experience] にアクセスできます。

## <a name="interpreting-productivity-score"></a>生産性スコアを解釈する 

[プロダクティビティスコア] ホームページには、カテゴリごとの総得点と得点履歴と主要な洞察が表示されます。

![生産性スコアのホームページ](../../media/pslanding.png)

**スコア** は、パーセント値とポイントで表されます。 分子にポイントと、分母に可能な最大ポイントが表示されます。

**ピアベンチマーク** を使用すると、自分のスコアを自分のような組織と比較することができます。 People エクスペリエンスカテゴリの場合、ピアベンチマーク測定値は、同様の組織のセット内のメジャーの平均として計算されます。 このセットは、ライセンスが付与されたユーザーの数、ライセンス、業界、tenure の種類がある、地域内の組織で構成されています (Microsoft 365 を使用)。 

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

このレポートは、ビジネスリーダーが理解しやすくなります。 

- Shift キーを押したときのリモート処理によるコラボレーションと通信への影響 

- ユーザーが自宅から作業するために調整したときのワークライフバランスへの影響。 

- リモート会議が効果的な意思決定をサポートしている場合。

[ビジネス継続性レポートの詳細情報](https://aka.ms/bcrps)

[Microsoft Graph の詳細情報](https://docs.microsoft.com/graph/)

## <a name="we-want-to-hear-from-you"></a>ご意見をお聞かせください。

生産性スコアに関する考えと、それを改善する方法についてのアイデアを共有します。 製品内の **フィードバック** セクションを使用して、ProductivityScorePreview@service.microsoft.com の生産性スコアチームに連絡します。
