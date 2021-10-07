---
title: ベースラインMicrosoft 365 Lighthouse展開する
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseベースラインを展開する方法Microsoft 365 Lighthouseします。
ms.openlocfilehash: d449a7677e478111590a2fbeedfbd211e07d7027
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173201"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>ベースラインMicrosoft 365 Lighthouse展開する 

> [!NOTE]
> この記事で説明する機能はプレビューで、変更される可能性があります。要件を満たすパートナーだけが [利用できます](m365-lighthouse-requirements.md)。 組織にアカウントが設定されていない場合Microsoft 365 Lighthouse[を参照してください](m365-lighthouse-sign-up.md)Microsoft 365 Lighthouse。

Microsoft 365 Lighthouse基準を使用すると、標準的な管理テナント構成を展開して、顧客テナント内のユーザー、デバイス、およびデータをセキュリティで保護できます。 ライトハウスに標準で提供される 6 つの既定のベースライン構成があります。

- 管理者に MFA を要求する
- エンド ユーザーに MFA を要求する
- 従来の認証をブロックする
- [デバイス登録の設定] Microsoft エンドポイント マネージャー – Azure AD参加
- デバイスの Defender ウイルス対策ポリシーをWindowsする
- デバイスのコンプライアンス ポリシーをWindowsする

## <a name="before-you-begin"></a>はじめに

ユーザーと顧客テナントが「要件」に記載されている要件を満[た](m365-lighthouse-requirements.md)していることを確認Microsoft 365 Lighthouse。

## <a name="learn-more-about-the-default-baseline"></a>既定の基準計画の詳細

左側 **のナビゲーション ウィンドウから** [基準計画] を選択して、[基準計画] ページを開きます。 既定の基準計画が既定のテナント グループ (すべてのテナント) に既に追加されているのが表示されます。 既定の基準計画構成を表示するには、[基準計画の表示] を **選択して** [既定の基準計画] ページを開きます。 構成は展開手順として一覧表示されます。 展開の詳細とユーザーへの影響を表示するには、展開手順を選択します。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="[既定の基準計画] ページのスクリーンショット。>。":::

## <a name="deploy-a-baseline-configuration"></a>ベースライン構成の展開  

1. 左側のナビゲーション ページで、[ **テナント** ] を選択して、オンボードテナントの一覧を表示します。

2. ベースライン構成を展開するテナントを選択します。

3. [展開 **計画] タブ** を選択すると、テナントの展開計画に追加されたベースラインのすべての展開手順が表示されます。

4. 展開手順を選択して、展開手順ページを開きます。

5. [ **適用] を** 選択して、選択した展開手順をテナントに適用します。 展開手順に 「このアクションには手動の手順が必要です」と示されている場合は、展開手順が正しく適用されるように手動手順を完了してください。

## <a name="related-content"></a>関連コンテンツ

[基準計画を使用して標準テナント構成を](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) 展開する概要 (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)