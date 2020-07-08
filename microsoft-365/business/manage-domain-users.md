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
description: ドメイン制御されたユーザーを Microsoft 365 for business と同期します。
ms.openlocfilehash: af9cb7c9b2b639edc2375679a73ab41c4cf6de71
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080061"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>ドメイン ユーザーを Microsoft 365 に同期する

## <a name="1-prepare-for-directory-synchronization"></a>1. ディレクトリ同期の準備 

ローカル Active Directory ドメインからユーザーとコンピューターを同期する前に、「 [Microsoft 365 へのディレクトリ同期の準備](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization)」を参照してください。 特に次のようになります。

   - 次の属性について、ディレクトリに重複が存在しないことを確認してください。 **mail**、 **ProxyAddresses**、および**userPrincipalName**。 これらの値は一意である必要があり、重複して削除する必要があります。
   
   - 各ローカルユーザーアカウントの**userPrincipalName** (UPN) 属性を、ライセンスされた Microsoft 365 ユーザーに対応するプライマリ電子メールアドレスと一致するように構成することをお勧めします。 例: mary.shelley@contoso.com ではなく*mary@contoso* 、 *mary.shelley@contoso.com*
   
   - Active Directory ドメインが、 *.com*または *.org*などのインターネットでルーティング可能なサフィックスの代わりに、*ローカル*ユーザーアカウントの UPN サフィックスではなく、ルーティング可能*ではない*サフィックスで終わっている場合は、「[ディレクトリ同期のために非ルーティングドメインを準備する](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)」で説明されているように、まずローカルユーザーアカウントの UPN サフィックスを調整します。 

手順 4 (4) の**実行 IdFix**を使用して、オンプレミスの Active Directory がディレクトリ同期の準備が整っていることを確認することもできます。

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect をインストールして構成します。

ユーザー、グループ、および連絡先をローカルの Active directory から Azure Active Directory に同期するには、Azure Active Directory Connect をインストールし、ディレクトリ同期をセットアップします。 

 1. 管理センターで、 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 左側のナビゲーションの [**セットアップ**の選択] をクリックします。

 2. [**サインインとセキュリティ**] で、[**組織のディレクトリからユーザーを同期する] の**下にある [**表示**] を選択します。

 3. [**組織のディレクトリからユーザーを同期**する] ページで、[**開始**] を選択します。

 4. 最初のステップ実行 IdFix ツールで、ディレクトリ同期の準備をします。

 5. ウィザードの手順に従って、Azure AD Connect をダウンロードし、それを使用して、ドメイン制御されたユーザーを Microsoft 365 に同期させます。


詳細については、「 [Microsoft 365 のディレクトリ同期をセットアップ](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)する」を参照してください。

Azure AD Connect のオプションを構成する際には、**パスワード同期**、**シームレスなシングルサインオン**、**パスワード書き戻し**機能を有効にすることをお勧めします。これは、Microsoft 365 for business でもサポートされています。

> [!NOTE]
> Azure AD Connect のチェックボックスを超えてパスワードを書き戻しするには、いくつかの追加の手順があります。 詳細については、「[方法: パスワードの書き戻しを構成](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)する」を参照してください。 

ドメインに参加している Windows 10 デバイスも管理する場合は、「[ドメインに参加している windows 10 デバイスを Microsoft 365 Business Premium で管理されるよう](manage-windows-devices.md)にする」を参照して、ハイブリッド Azure AD Join を設定してください。 