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
description: Microsoft 365 Business Premium のセットアップ手順、サブスクライブからドメインとユーザーの追加、セキュリティ ポリシーの設定などについて説明します。
ms.openlocfilehash: 749acbfdbde92ad97b09dc720c85dd850b76c9cf
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579936"
---
# <a name="overview-of-setup"></a>セットアップの概要

Microsoft 365 Business Premium のセットアップに関する短いビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

ほとんどのセットアップ手順はガイド付きセットアップで実行できますが、他のオプションも一覧表示されます。

## <a name="step-1-add-your-domain-and-users"></a>手順 1: ドメインとユーザーを追加する

   - **[ドメインを追加](set-up.md#add-your-domain-to-personalize-sign-in)** します (サインアップ中にドメインを購入した [場合、この](sign-up.md)手順は既に完了しています)。

   - **ユーザーを追加します**。 次の 3 つの方法でユーザーを追加できます。
        - ガイド付 [きセットアップで](set-up.md#add-users-in-the-wizard).
        - オンプレミスの Active ディレクトリがある場合は、 [ディレクトリ同期を使用して Azure AD Connect](../enterprise/set-up-directory-synchronization.md) を使用してユーザーを追加します。
        - 後で [管理センターでユーザー](../admin/add-users/add-users.md) を追加することもできます。
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>手順 2: セキュリティ ポリシーを設定し、デバイスを構成する 

  - ガイド付 [きセットアップを使用して](set-up.md#protect-your-organization) デバイス ポリシーを構成します。 
  - 管理センターと Intune ポータルで、後で[](view-policies-and-devices.md)追加または編集[することもできます](/intune/tutorial-walkthrough-intune-portal)。
  - セットアップ ウィザードでは、基本的な脅威保護とデータ損失防止の設定もセットアップされます。
  
  セットアップ ウィザードのセキュリティ設定に加えて、次の設定を追加することでセキュリティを強化できます。

- **電子メールマルウェア保護**
- **Defender for Office 365 でのフィッシング対策**
- **Exchange Online Archiving**
- **Azure Information Protection (Plan1)**

開始するには、「脅威の保護 [を強化し、](increase-threat-protection.md) コンプライアンス [機能を設定する」を参照してください](set-up-compliance.md)。

ベスト セキュリティ プラクティスのロード マップについては [、「Microsoft 365 Business Premium](/office365/admin/security-and-compliance/secure-your-business-data) をセキュリティで保護する上位 10 の方法」も参照してください。

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>手順 3: Windows 10 デバイスのセットアップと管理

ガイド付きセットアップが完了したら、組織内のすべての Windows 10 コンピューターを保護する必要があります。
  
- Windows 10 Pro[](pre-requisites-for-data-protection.md)は Microsoft 365 Business Premium の前提条件ですが、Windows 7 Pro、Windows 8 Pro、または Windows 8.1 Pro を使用している場合、サブスクリプションは[Windows 10 Pro](./upgrade-to-windows-pro-creators-update.md)へのアップグレードを受ける権利があります。
- セキュリティで保護された [Windows 10 PC](secure-win-10-pcs.md) の手順に従って、Windows 10 デバイスのポリシーを設定します。

Windows 10 デバイスを Azure ADに参加すると、Windows 10 コンピューターに設定したポリシーが適用されます。 詳細については [、「Microsoft 365 ユーザー向け Windows デバイスのセットアップ」を参照してください](set-up-windows-devices.md)。

## <a name="step-4-install-microsoft-365-apps-for-business"></a>手順 4: Microsoft 365 Apps for business をインストールする
- セットアップ ウィザードを使用Office Windows デバイスに自動的にインストール [できます](set-up.md#deploy-office-365-client-apps)。
- ユーザーが [Windows とデバイスOfficeアプリ](/office365/admin/setup/install-applications) をインストールできます。
     
## <a name="advanced"></a>詳細情報
- **Autopilot を使用して新しいデバイスをセットアップする**
            
     [Windows Autopilot](add-autopilot-devices-and-profile.md)を使用すると、ユーザー用 **に新しい** Windows 10 デバイスを自動的に事前構成できますが、[](https://www.microsoft.com/solution-providers/search)これを行えるパートナーを取得する方が簡単な場合があります。 また [、Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)にアクセスし、クラウド テクノロジの専門家に、購入した新しいデバイスのセットアップを求めすることもできます。

- **オンプレミス リソースへのアクセス**

     - 組織で Windows Server Active Directory をオンプレミスで使用している場合は、ローカル認証を必要とするオンプレミス リソースへのアクセスを維持しながら、Windows 10 デバイスを保護するために Microsoft 365 Business Premium をセットアップできます。 「ドメインに参加している Windows 10 デバイスを [Microsoft 365 Business Premium](manage-windows-devices.md) で管理するを有効にする」の手順に従って、これを設定します。 これは推奨される方法であり、この状態のデバイスはハイブリッド Azure と呼ばADデバイスです。

    - ビジネスに、いくつかのオンプレミス リソース (ファイル共有やプリンターなど) が含まれるローカル Active Directory がある場合は [、Microsoft 365 Business Premium](access-resources.md)の Azure AD に参加しているデバイスからオンプレミスリソースにアクセスする手順に従って、Azure AD に参加しているデバイスにこれらのリソースへのアクセス権を与えることができます。

## <a name="see-also"></a>関連項目

[一般法人向け Microsoft 365 のトレーニング ビデオ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)