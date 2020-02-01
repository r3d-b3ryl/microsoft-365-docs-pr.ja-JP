---
title: 手順の概要
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 Business のセットアップ手順の概要。
ms.openlocfilehash: 07cbd4fd187f78474783db848ac9b69068d2b44a
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595067"
---
# <a name="overview-of-setup"></a>手順の概要

Microsoft 365 Business のセットアップに関する短いビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

このビデオがお役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

セットアップの手順のほとんどはセットアップウィザードで行うことができますが、その他のオプションも表示されます。

## <a name="step-1-add-your-domain-and-users"></a>手順 1: ドメインとユーザーを追加する

   - **[ドメインを追加](set-up.md#add-your-domain-to-personalize-sign-in)** します ([サインアップ](sign-up.md)中にドメインを購入した場合、この手順は既に完了しています)。

    - **ユーザーを追加**します。 次の3つの方法のいずれかでユーザーを追加できます。
        - [ウィザード](set-up.md#add-users-in-the-wizard)で。
        - オンプレミスの Active directory を使用している場合は、ディレクトリ同期を使用して、 [AZURE AD Connect を使用してユーザーを追加](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)します。
        - 後で管理センターで[ユーザーを追加](add-users-m365b.md)することもできます。
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>手順 2: セキュリティポリシーを設定し、デバイスを構成する 

  - [セットアップウィザード](set-up.md#protect-your-organization)を使用して、デバイスポリシーを構成します。 
  - また、後で[管理センター](view-policies-and-devices.md)および[Intune ポータル](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)で追加または編集することもできます。
  - また、セットアップウィザードによって、基本的な脅威保護とデータ損失防止の設定も設定されます。
  
  セットアップウィザードのセキュリティ設定に加えて、次の設定を追加することによって、セキュリティを向上させることができます。

- **メールマルウェア対策**
- **ATP のフィッシング対策**
- **Exchange Online Archiving**
- **Azure Information Protection (Plan1**)

開始するには、「[脅威保護を強化](increase-threat-protection.md)する」と「[コンプライアンス機能をセットアップ](set-up-compliance.md)する」を参照してください。

セキュリティに関するベストプラクティスのロードマップについては[、Microsoft 365 Business をセキュリティで保護するための10のトップの方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data)も参照してください。

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>手順 3: Windows 10 デバイスをセットアップおよび管理する

セットアップウィザードを実行した後は、組織内のすべての Windwos 10 コンピューターを使用する必要があります。
  
- Windows 10 Pro は Microsoft 365 Business の[前提条件](pre-requisites-for-data-protection.md)ですが、Windows 7 Pro、Windows 8 pro、または Windows 8.1 Pro をご利用の場合は、サブスクリプションで[windows 10 pro へのアップグレード](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)をお勧めします。
- 「 [Windows 10 pc をセキュリティ保護](secure-win-10-pcs.md)する」の手順に従って、windows 10 デバイスのポリシーを設定します。

Windows 10 デバイスを Azure AD に参加させると、Windows 10 コンピューターに設定したポリシーが適用されます。 詳細については、「 [Microsoft 365 Business ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md)」を参照してください。

## <a name="step-4-install-office-365-business"></a>手順 4: Office 365 Business をインストールする
- [セットアップウィザード](set-up.md#deploy-office-365-client-apps)を使用して、Windows デバイスに Office を自動的にインストールすることができます。
- ユーザーが Windows およびデバイス用の[Office アプリをインストール](https://docs.microsoft.com/office365/admin/setup/install-applications)できるようにします。
     
## <a name="advanced"></a>詳細設定
- **自動操縦を使用して新しいデバイスをセットアップする**
            
     [Windows 自動操縦](add-autopilot-devices-and-profile.md)を使用して、ユーザーに対して**新しい**windows 10 デバイスを自動的に事前構成することができますが、これを実行できる[パートナー](https://www.microsoft.com/solution-providers/search)を取得する方が簡単な場合があります。 [Microsoft ストア](https://go.microsoft.com/fwlink/?linkid=874598)に移動し、クラウドテクノロジエキスパートに依頼して、購入する新しいデバイスをセットアップすることもできます。

- **オンプレミス リソースへのアクセス**

     - 組織がオンプレミスの Windows Server Active Directory を使用している場合は、Windows 10 のデバイスを保護するように Microsoft 365 Business をセットアップし、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持することができます。 「[ドメインに参加している Windows 10 デバイスが Microsoft 365 Business で管理される](manage-windows-devices.md)ようにする」の手順に従って、これを設定します。 この方法をお勧めします。この状態のデバイスは、ハイブリッド Azure AD 参加デバイスと呼ばれます。

    - オンプレミスのリソース (ファイル共有やプリンターなど) を含むローカルな Active Directory が企業にある場合は、「 [Microsoft 365 business の AZURE ad に参加しているデバイスからオンプレミスのリソースにアクセスする」](access-resources.md)の手順に従って、azure ad に参加しているデバイスにこれらのリソースへのアクセス権を付与できます。

## <a name="see-also"></a>関連項目

[Microsoft 365 Business のトレーニング ビデオ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
