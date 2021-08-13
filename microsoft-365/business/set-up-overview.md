---
title: セットアップの概要
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: サブスクリプションからサブスクライブ、ドメインMicrosoft 365 Business Premium追加、セキュリティ ポリシーの設定など、ユーザーの設定手順について説明します。
ms.openlocfilehash: 7c09dca354781bf92f6bbecca0f3fb9875fb654515fe35c2f96cc780a894a764
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53803224"
---
# <a name="overview-of-setup"></a>セットアップの概要

セットアップに関する短いビデオMicrosoft 365 Business Premium見る。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](../business-video/index.yml)」をご覧ください。

ほとんどのセットアップ手順はガイド付きセットアップで実行できますが、他のオプションも一覧表示されます。

## <a name="step-1-add-your-domain-and-users"></a>手順 1: ドメインとユーザーを追加する

   - **[ドメインを追加](set-up.md#add-your-domain-to-personalize-sign-in)** します (サインアップ中にドメインを購入した [場合、この](sign-up.md)手順は既に完了しています)。

   - **ユーザーを追加します**。 次の 3 つの方法でユーザーを追加できます。
        - ガイド付 [きセットアップで](set-up.md#add-users-in-the-wizard).
        - オンプレミスの Active ディレクトリがある場合は、[ディレクトリ同期を使用](../enterprise/set-up-directory-synchronization.md)して Azure AD Connectを使用してユーザーを追加します。
        - 後で [管理センターでユーザー](../admin/add-users/add-users.md) を追加することもできます。
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>手順 2: セキュリティ ポリシーを設定し、デバイスを構成する 

  - ガイド付 [きセットアップを使用して](set-up.md#protect-your-organization) デバイス ポリシーを構成します。 
  - 管理センターと Intune ポータルで、後で[](view-policies-and-devices.md)追加または編集[することもできます](/intune/tutorial-walkthrough-intune-portal)。
  - セットアップ ウィザードでは、基本的な脅威保護とデータ損失防止の設定もセットアップされます。
  
  セットアップ ウィザードのセキュリティ設定に加えて、次の設定を追加することでセキュリティを強化できます。

- **電子メールマルウェア保護**
- **Defender for Office 365**
- **Exchange Online Archiving**
- **Azure Information Protection (Plan1)**

開始するには、「脅威の保護 [を強化し、](increase-threat-protection.md) コンプライアンス [機能を設定する」を参照してください](set-up-compliance.md)。

ベスト セキュリティ プラクティスのロード マップについては、Microsoft 365 Business Premiumセキュリティを保護するトップ[10](/office365/admin/security-and-compliance/secure-your-business-data)の方法も参照してください。

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>手順 3: デバイスのセットアップと管理Windows 10する

ガイド付きセットアップが完了したら、組織内のすべてのコンピューター Windows 10保護する必要があります。
  
- Windows 10 Pro Microsoft 365 Business Premium の前提条件[](pre-requisites-for-data-protection.md)ですが、Windows 7 Pro、Windows 8 Pro、または Windows 8.1 Pro がある場合、サブスクリプションは Windows 10 Pro へのアップグレード[を受ける権利があります](./upgrade-to-windows-pro-creators-update.md)。
- セキュリティで保護されたデバイス[PC のWindows 10手順に](secure-win-10-pcs.md)従って、デバイスのポリシー Windows 10します。

デバイスを Azure Windows 10に参加AD、コンピューターに設定Windows 10ポリシーが適用されます。 詳細については、「ユーザーのデバイス[をWindowsする」をMicrosoft 365してください](set-up-windows-devices.md)。

## <a name="step-4-install-microsoft-365-apps-for-business"></a>手順 4: インストールMicrosoft 365 Apps for business
- セットアップ ウィザードを使用Office、Windowsデバイスに自動的にインストール[できます](set-up.md#deploy-office-365-client-apps)。
- ユーザーが[アプリとデバイスOfficeアプリ](/office365/admin/setup/install-applications)をWindowsできます。
     
## <a name="advanced"></a>詳細情報
- **Autopilot を使用して新しいデバイスをセットアップする**
            
     Windows [Autopilot](add-autopilot-devices-and-profile.md)を使用すると、ユーザー用に新しい **Windows 10** デバイスを自動的に事前構成できますが、これを行えるパートナーを取得する [](https://www.microsoft.com/solution-providers/search)方が簡単な場合があります。 クラウド テクノロジの専門家[に](https://go.microsoft.com/fwlink/?linkid=874598)Microsoft Store、購入した新しいデバイスをセットアップすることもできます。

- **オンプレミス リソースへのアクセス**

     - 組織で Windows Server Active Directory オンプレミスを使用している場合は、Microsoft 365 Business Premium をセットアップして Windows 10 デバイスを保護しながら、ローカル認証を必要とするオンプレミス リソースへのアクセスを維持できます。 「ドメインに参加しているデバイスをWindows 10[する](manage-windows-devices.md)」の手順に従って、Microsoft 365 Business Premiumを設定します。 これは推奨される方法であり、この状態のデバイスはハイブリッド Azure と呼ばADデバイスです。

    - 一部のオンプレミス リソース (ファイル共有やプリンターなど) を含むローカル Active Directory がビジネスにある場合は、azure AD に参加しているデバイスにこれらのリソースへのアクセス権を与えることができます。この手順は[、「Microsoft 365 Business Premium](access-resources.md)の Azure AD に参加しているデバイスからオンプレミス リソースにアクセスする」を参照してください。

## <a name="related-content"></a>関連コンテンツ

[一般法人向け Microsoft 365 のトレーニング ビデオ](../business-video/index.yml) (リンク ページ)