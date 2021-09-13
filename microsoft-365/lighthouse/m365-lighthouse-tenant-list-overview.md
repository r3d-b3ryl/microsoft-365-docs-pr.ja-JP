---
title: Microsoft 365 Lighthouseリストの概要
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseの一覧について説明します。
ms.openlocfilehash: 13481ecbaaf20c5886837e03f4a606531548145e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59211733"
---
# <a name="microsoft-365-lighthouse-tenant-list-overview"></a>Microsoft 365 Lighthouseリストの概要

> [!NOTE]
> この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。 組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。

テナントMicrosoft 365 Lighthouseリストには、契約しているさまざまなテナント (ライトハウスに対するテナントオンボーディングの状態など) に関する分析情報が表示されます。 テナントリストでは、テナントにタグを付け、ライトハウス全体で異なるフィルターを提供し、特定のテナントとその展開計画の状態について詳しくは、ドリルダウンしてください。

テナントがライトハウスのオンボーディング [要件](m365-lighthouse-requirements.md)を満たした後、テナントの一覧に状態が **[アクティブ** ] と表示されます。

ライトハウスのテナントリストにアクセスするには、左側のナビゲーション ウィンドウで [テナント] を選択して [テナント] ページを開きます。

## <a name="tenant-status"></a>テナントの状態

次の表に、さまざまな状態メッセージとその意味を示します。<br><br>

| ステータス メッセージ | 説明 |
|--|--|
| Active | オンボーディングとデータ フローが開始されました。 |
| プロセス中 | テナントが検出されましたが、完全にはオンボードされません。 |
| 不適格、DAP | 委任された管理者特権 (DAP) のセットアップが必要です。 |
| 不適格、ユーザー数 | テナントには、許可されているユーザーよりも多くのユーザーがあります。 |
| 不適格、ライセンス | テナントに必要なライセンスはありません。 |
| 不適格なコントラクトの種類 | CSP クラウド ソリューション プロバイダー (CSP) コントラクトが必要です。 |
| 非アクティブ | テナントがアクティブではなくなりました。 |

テナントを無効にした後、ライトハウスが非アクティブ化プロセスを完了している間、テナントに対してアクションを実行できません。 非アクティブ化が完了するために最大 48 時間かかる場合があります。

テナントを再アクティブ化する場合、データが再び表示されるには最大 48 時間かかる場合があります。

## <a name="tenant-tags"></a>テナント タグ

顧客テナントには、ライトハウス内のカスタム ラベルをタグ付けできます。 これらのタグは、テナントを整理するために使用できます。また、関連する顧客テナントのセットで使用できる既存のビューと分析情報を簡単にフィルター処理するのに役立ちます。 [テナント] ページから、タグと割り当てられているテナントを管理することもできます。

## <a name="related-content"></a>関連コンテンツ

[ユーザーのMicrosoft 365 Lighthouse](m365-lighthouse-requirements.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)