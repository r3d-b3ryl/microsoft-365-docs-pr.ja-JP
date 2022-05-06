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
description: ドメインが制御するユーザーをビジネス向けのMicrosoft 365と同期します。
ms.openlocfilehash: 6a00b76113a750f306ef6545f1b38fcf9f9b2202
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634539"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>ドメイン ユーザーを Microsoft 365 に同期する

## <a name="1-prepare-for-directory-synchronization"></a>1. ディレクトリ同期の準備 

ローカル Active Directory ドメインからユーザーとコンピューターを同期する前に、「[Microsoft 365へのディレクトリ同期の準備」を](../../enterprise/prepare-for-directory-synchronization.md)参照してください。 特に、

   - **メール**、**proxyAddresses**、**userPrincipalName** という属性について、ディレクトリに重複がないことを確認します。 これらの値は一意である必要があり、重複するものはすべて削除する必要があります。
   
   - ライセンスMicrosoft 365 ユーザーに対応するプライマリ 電子メール アドレスと一致するように、ローカル ユーザー アカウントごとに **userPrincipalName** (UPN) 属性を構成することをお勧めします。 たとえば、*mary@contoso.local ではなく mary.shelley@contoso.com* 
   
   - Active Directory ドメインが、.*com* や .*org* などのインターネットルーティング可能なサフィックスの代わりに *、.local* や *.lan* などのルーティング不可能なサフィックスで終わる場合は、「[ディレクトリ同期のためにルーティング不可能なドメインを準備](../../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)する」の説明に従って、ローカル ユーザー アカウントの UPN サフィックスを最初に調整します。 

以下の手順 4 (4) の **実行 IdFix** では、オンプレミスの Active Directoryがディレクトリ同期の準備ができていることも確認します。

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connectをインストールして構成する

ローカル Active Directory のユーザー、グループ、連絡先をAzure Active Directoryに同期するには、Azure Active Directory Connectをインストールしてディレクトリ同期を設定します。 

 1. [管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で、左側のナビゲーションで **[セットアップ]** を選択します。

 2. [ **サインインとセキュリティ] で**、[ **ユーザーを Microsoft アカウントに追加または同期**] を選択します。

 3. [**Microsoft アカウントへのユーザーの追加または同期**] ページで、**概要** を選択します。

 4. 最初の手順では、IdFix ツールを実行してディレクトリ同期の準備を行います。

 5. ウィザードの手順に従ってAzure AD Connectをダウンロードし、それを使用してドメインで制御されたユーザーをMicrosoft 365に同期します。


詳細については、「[Microsoft 365のディレクトリ同期を設定](../../enterprise/set-up-directory-synchronization.md)する」を参照してください。

Azure AD Connectのオプションを構成するときは、**パスワード同期**、**シームレス シングル サインオン**、パスワード **ライトバック** 機能を有効にすることをお勧めします。これは、ビジネス向けのMicrosoft 365でもサポートされています。

> [!NOTE]
> Azure AD Connectのチェック ボックスを超えて、パスワード ライトバックの追加手順がいくつかあります。 詳細については、「 [方法: パスワード ライトバックを構成する」を](/azure/active-directory/authentication/howto-sspr-writeback)参照してください。 

ドメイン参加済みWindows 10 デバイスも管理する場合は、「[Microsoft 365 Business Premiumによってドメイン参加済みWindows 10デバイスを管理できるようにする](../../business-premium/m365bp-manage-windows-devices.md)」を参照して、ハイブリッド Azure AD参加を設定します。
