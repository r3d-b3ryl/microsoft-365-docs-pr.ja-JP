---
title: ドメイン ユーザーを Microsoft 365 に同期する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: ドメイン制御ユーザーと Microsoft 365 for business を同期します。
ms.openlocfilehash: 1c939dec7229f02991b15f08c48f184efecaddb0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913256"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>ドメイン ユーザーを Microsoft 365 に同期する

## <a name="1-prepare-for-directory-synchronization"></a>1. ディレクトリ同期の準備 

ローカルの Active Directory ドメインからユーザーとコンピューターを同期する前に、「ディレクトリ同期の準備 [を Microsoft 365](../enterprise/prepare-for-directory-synchronization.md)に準備する」を参照してください。 特に、

   - **mail、proxyAddresses、userPrincipalName** という属性の重複がディレクトリに存在しなかから **なか確認してください**。 これらの値は一意である必要があります。重複は削除する必要があります。
   
   - ライセンスを受け取った Microsoft 365 ユーザーに対応するプライマリ メール アドレスと一致するローカル ユーザー アカウントごとに **userPrincipalName** (UPN) 属性を構成することをお勧めします。 たとえば、mary.shelley@contoso.com.local ではなくmary@contoso *を指定します。* 
   
   - Active Directory ドメインが *、.com* や *.org* などのインターネットで出力可能なサフィックスの代わりに *、.local* や *.lan* などの出力不可のサフィックスで終わる場合は、「ディレクトリ同期用にラウ [](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)ト可能でないドメインを準備する」の説明に従って、最初にローカル ユーザー アカウントの UPN サフィックスを調整します。 

以下 **の手順** 4 (4) で IdFix を実行すると、オンプレミスの Active Directory がディレクトリ同期の準備ができていることを確認します。

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect のインストールと構成

ローカルの Active Directory から Azure Active Directory にユーザー、グループ、連絡先を同期するには、Azure Active Directory Connect をインストールし、ディレクトリ同期を設定します。 

 1. 管理センター [で、左側](https://go.microsoft.com/fwlink/p/?linkid=2024339)の **ナビゲーションで [セットアップ** ] を選択します。

 2. [ **サインインとセキュリティ] で、[** 組織 **のディレクトリ**  からユーザーを同期する] の下の [表示 **] を選択します**。

 3. [組織 **のディレクトリからユーザーを** 同期する] ページで、[開始] **を選択します**。

 4. 最初の手順では、IdFix ツールを実行してディレクトリ同期を準備します。

 5. ウィザードの手順に従って Azure AD Connect をダウンロードし、それを使用してドメイン制御ユーザーを Microsoft 365 に同期します。


詳細 [については、「Microsoft 365](../enterprise/set-up-directory-synchronization.md) のディレクトリ同期をセットアップする」を参照してください。

Azure AD Connect のオプションを構成する場合は、ビジネス向けMicrosoft 365 でもサポートされるパスワード同期、シームレス シングル サインオン、およびパスワード ライトバック機能を有効にすることをお勧めします。 

> [!NOTE]
> Azure AD Connect のチェック ボックスを超えてパスワードの書き戻しを行うADがあります。 詳細については [、「How-to: configure password writeback」を参照してください](/azure/active-directory/authentication/howto-sspr-writeback)。 

ドメインに参加している Windows 10 デバイスも管理する場合は、「ドメインに参加している Windows 10 デバイスを [Microsoft 365 Business Premium](manage-windows-devices.md) で管理してハイブリッド Azure AD Join をセットアップする」を参照してください。