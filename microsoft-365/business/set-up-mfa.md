---
title: 多要素認証をセットアップする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
description: Microsoft 365 Business で多要素認証をセットアップします。
ms.openlocfilehash: 59a3ff7a9494ccfc44fa701c6f605a9bd9eeafcf
ms.sourcegitcommit: 5d11f516e78ea4a74145e19ba2300f0792c8bac1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/19/2019
ms.locfileid: "38715059"
---
# <a name="multi-factor-authentication"></a>多要素認証

多要素認証 (MFA) では、ユーザーは2番目の方法でサインインして、電話またはオーセンティケータアプリで自分の身元を確認する必要があります。

## <a name="set-up-mfa-in-the-microsoft-365-admin-center"></a>Microsoft 365 管理センターで MFA をセットアップする

[![管理センターについて知らせるラベルが変更されていますので、詳細については、aka.ms/aboutM365preview を参照してください。](media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

1. グローバル管理者の資格情報を使用して、 [Microsoft 365 管理センター](https://admin.microsoft.com)にサインインします。 
2. 左側のナビゲーションで、[**セットアップ**] を選択します。
3. [セットアップ] ページで、[**多要素認証 (MFA) カードを有効にする** **] を選択し**ます。
4. [ **Mfa を有効**にする] ページで、[**開始**] を選択するか、既に MFA を設定して変更を行う場合は [**管理**] を選択します。 

  :::image type="content" source="media/turnonmfa.png" alt-text="[MFA] ページを有効にするスクリーンショット。":::

5. [**サインインセキュリティを強化**する] パネルで、[**管理者に対して多要素認証を必要とする**] の両方をオンにして、[ポリシーの**作成**] を選択します。
