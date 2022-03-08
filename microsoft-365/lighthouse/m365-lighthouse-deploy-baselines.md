---
title: ベースラインMicrosoft 365 Lighthouse展開する
f1.keywords: CSH
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
description: 管理サービス プロバイダー (MSP) の場合は、Microsoft 365 Lighthouseベースラインを展開する方法Microsoft 365 Lighthouse説明します。
ms.openlocfilehash: fa443fa025f0a1ffba6a230427797755611328a3
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324628"
---
# <a name="deploy-microsoft-365-lighthouse-baselines"></a>ベースラインMicrosoft 365 Lighthouse展開する 

Microsoft 365 Lighthouse基準を使用すると、標準的な管理テナント構成を展開して、顧客テナント内のユーザー、デバイス、およびデータをセキュリティで保護できます。 ライトハウスに標準で提供される 7 つの既定のベースライン構成があります。

- 管理者に MFA を要求する
- エンド ユーザーに MFA を要求する
- 従来の認証をブロックする
- [デバイス登録の設定] - Microsoft エンドポイント マネージャー参加Azure ADする
- Defender ウイルス対策ポリシーの構成 (Windows 10以降)
- Microsoft Defender Firewall for Windows 10以降
- コンプライアンス ポリシーの構成 (Windows 10以降)

## <a name="before-you-begin"></a>始める前に

ユーザーと顧客テナントが「要件」に記載されている要件を満[たしていることを確認](m365-lighthouse-requirements.md)Microsoft 365 Lighthouse。

## <a name="learn-more-about-the-default-baseline"></a>既定の基準計画の詳細

[ **基準計画] ページ** を開くには、ライトハウスの左側のナビゲーション ウィンドウから [基準計画] を選択します。 既定の基準計画が既定のテナント グループ (すべてのテナント) に既に追加されているのが表示されます。 既定の基準計画構成を表示するには、[基準計画の表示] を **選択して** [既定の基準計画] ページを開きます。 構成は展開手順として一覧表示されます。 展開の詳細とユーザーへの影響を表示するには、展開手順を選択します。

:::image type="content" source="../media/m365-lighthouse-deploy-baselines/default-baseline-page.png" alt-text="[既定の基準計画] ページのスクリーンショット。":::

## <a name="deploy-a-baseline-configuration"></a>ベースライン構成の展開  

1. ライトハウスの左側のナビゲーション ウィンドウで、[ **テナント] を選択** して、オンボードテナントの一覧を表示します。

2. ベースライン構成を展開するテナントを選択します。

3. [展開 **計画] タブ** を選択すると、テナントの展開計画に追加されたベースラインのすべての展開手順が表示されます。

4. 展開手順を選択して、展開手順ページを開きます。

5. [ **確認] と [適用]** を選択して、選択した展開手順をテナントに適用します。 展開手順に 「このアクションには手動の手順が必要です」と示されている場合は、展開手順が正しく適用されるように手動手順を完了してください。

## <a name="related-content"></a>関連コンテンツ

[基準計画を使用して標準テナント構成を](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) 展開する概要 (記事)\
[Microsoft 365のテナント ページの概要](m365-lighthouse-tenants-page-overview.md) (記事)\
[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (記事)\
[ポータル Microsoft 365 Lighthouseの構成](m365-lighthouse-configure-portal-security.md) (記事) 