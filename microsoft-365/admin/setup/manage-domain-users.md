---
title: ドメイン ユーザーを Microsoft 365 に同期する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
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
description: ドメイン制御ユーザーとビジネス向けMicrosoft 365同期します。
ms.openlocfilehash: 6a00b76113a750f306ef6545f1b38fcf9f9b2202
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634539"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>ドメイン ユーザーを Microsoft 365 に同期する

## <a name="1-prepare-for-directory-synchronization"></a>1. ディレクトリ同期の準備 

ローカル サーバーからユーザーとコンピューターを同期する前Active Directory ドメイン、「[ディレクトリ](../../enterprise/prepare-for-directory-synchronization.md)同期の準備」を参照Microsoft 365。 特に、

   - mail、**proxyAddresses**、**userPrincipalName** という属性の重複がディレクトリに存在しなかからなか確認してください。 これらの値は一意である必要があります。重複は削除する必要があります。
   
   - 各ローカル ユーザー アカウントの **userPrincipalName** (UPN) 属性を、ライセンスを受け取ったユーザーに対応するプライマリ 電子メール アドレスと一致Microsoft 365することをお勧めします。 たとえば、*mary.shelley@contoso.com.local ではなくmary@contosoを指定します。* 
   
   - *Active* Directory ドメインが 、.com や .org などのインターネットで出力可能なサフィックスの代わりに *、.local* や [](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)*.lan* などの出力不可のサフィックスで終わる場合は、「ディレクトリ同期用にラウト可能でないドメインを準備する」の説明に従って、最初にローカル ユーザー アカウントの UPN サフィックスを調整します。 

以下 **の手順** 4 (4) で IdFix を実行すると、ディレクトリ同期オンプレミスの Active Directory準備ができていることを確認します。

## <a name="2-install-and-configure-azure-ad-connect"></a>2. インストールと構成Azure AD Connect

ローカル Active Directory のユーザー、グループ、連絡先をローカル Active Directory Azure Active Directory同期するには、Azure Active Directory Connectインストールしてディレクトリ同期を設定します。 

 1. 管理センター [で、左側](https://go.microsoft.com/fwlink/p/?linkid=2024339)の **ナビゲーションで [セットアップ** ] を選択します。

 2. [**サインインとセキュリティ] で、[****Microsoft アカウントにユーザーを追加または同期する] を選択します**。

 3. [ユーザーを **Microsoft アカウントに追加または同期する] ページで**、[ユーザーの追加または同期] **概要**。

 4. 最初の手順では、IdFix ツールを実行してディレクトリ同期を準備します。

 5. ウィザードの手順に従って、Azure AD Connectをダウンロードし、それを使用してドメイン制御ユーザーとユーザーを同期Microsoft 365。


詳細[については、「ディレクトリ同期のセットアップ」Microsoft 365](../../enterprise/set-up-directory-synchronization.md)参照してください。

Azure AD Connect のオプションを構成する場合は、パスワード同期、シームレス シングル サインオン、およびビジネス向け Microsoft 365 でもサポートされているパスワード ライトバック機能を有効にすることをお勧めします。

> [!NOTE]
> パスワードの書き戻しには、パスワードの書き戻しに関する追加の手順が、パスワード のチェック ボックスを超Azure AD Connect。 詳細については、「 [How-to: configure password writeback」を参照してください](/azure/active-directory/authentication/howto-sspr-writeback)。 

ドメインに参加している Windows 10 デバイスも管理する場合は、「Microsoft 365 Business Premium によって管理されるドメイン参加 [Windows 10](../../business-premium/m365bp-manage-windows-devices.md) デバイスを有効にしてハイブリッド Azure AD Join を設定する」を参照してください。
