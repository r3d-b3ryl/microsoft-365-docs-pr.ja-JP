---
title: Microsoft 365 for business の使用を開始する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- TRN_SMB
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Microsoft 365 for business、セットアップ方法、およびユーザーのデバイスと Pc を準備して Microsoft 365 for business で保護されていることを確認する方法について説明します。
ms.openlocfilehash: ec50036f589cfd8497b0e7e9af6519b30d25dcd3
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306491"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Microsoft 365 for business の使用を開始する

## <a name="what-is-microsoft-365-for-business"></a>Microsoft 365 for business とは

Microsoft 365 for business は、Outlook、Word、Excel、およびその他の Office 製品で常に最新の状態になる、ビジネスの生産性とコラボレーションツールの包括的なセットです。 管理が簡単なエンタープライズレベルのセキュリティを使用して、すべての iOS、Android、Windows 10 デバイス上の作業ファイルを保護することができます。

Microsoft 365 for business の簡単な概要については、このビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 for business は、最大300のライセンスを想定しています。 ライセンスの追加が必要な場合は、[Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986) のドキュメントで詳細を参照してください。 
  
## <a name="get-microsoft-365-for-business"></a>Microsoft 365 for business の入手

- パートナーがいる場合は、microsoft 365 for business を利用できます。 microsoft [パートナーセンターから microsoft 365 for business を入手](get-microsoft-365-business.md)してください。
    
- パートナーを持っておらず、Microsoft 365 for business を入手する場合は、 [ここで購入](https://www.microsoft.com/microsoft-365/business)できます。
    
## <a name="set-up-microsoft-365-for-business"></a>一般法人向け Microsoft 365 をセットアップする

 **Microsoft 365 for business スイートの概要セットアップ**
  
次の図では、管理者が Microsoft 365 for business をセットアップする方法について説明します。 また、Microsoft 365 for business 用に Windows Pc を準備する手順についても説明します。 [Windows 自動操縦](add-autopilot-devices-and-profile.md)を使用して、Microsoft 365 管理センターで新しいデバイスを追加することもできます。 自動操縦を使用して、ユーザーが Microsoft 365 for business の資格情報でサインインするとすぐに、生産性を高めるために新しいデバイスをセットアップして事前構成することができます。
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

このビデオでは、Microsoft 365 for business のセットアップの概要をご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

このビデオがお役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: Microsoft 365 for business のセットアップ (管理者向け)

グローバル管理者の資格情報を使用して [microsoft 365 管理センター](https://portal.office.com/adminportal/home) にサインインし、次の手順を実行して microsoft 365 for business を設定します。 
  
1. [Microsoft 365 for business を使用してデバイス上のデータを保護するための前提条件](pre-requisites-for-data-protection.md)
    
    最初に前提条件を読んで、デバイスの Microsoft 365 for business の準備が整っていることを確認してください。
    
2. [セットアップウィザードを使用して、Microsoft 365 for business をセットアップする](set-up.md)
    
    **ローカルの Active Directory からクラウドに完全に移動**する場合は、Microsoft 365 管理センターに移動し、セットアップウィザードを使用してユーザーを手動で追加するか、または Azure AD Connect を使用して1回限りの同期を行うことができます。 これを行うには 2 つの方法があります。 
    
    - Exchange 2010、Exchange 2013、または Exchange 2016 サーバーもある場合は、最小限の [ハイブリッドを使用して、exchange メールボックスを Microsoft 365 にすばやく移行](https://docs.microsoft.com/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)できます。 最低限のハイブリッド手順には、Azure AD へのユーザーの1回限りの同期と、オンプレミスからクラウドへの電子メールの移行が含まれます。 メールの移行が完了した後、この方法を使用すると、ディレクトリ同期は自動的に無効になります。
    
    - ディレクトリ同期ウィザードを使用して、ユーザーをクラウドに同期させます。 このプロセスを完了するには、「 [Microsoft 365 のディレクトリ同期のセットアップ](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) 」の手順を実行します。 ユーザーをクラウドに同期させた後、 [Microsoft 365 のディレクトリ同期を無効](https://docs.microsoft.com/microsoft-365/enterprise/turn-off-directory-synchronization)にする必要があります。
    
    また、このように追加された各ユーザーに、Microsoft 365 for business のライセンスを付与する必要があります。 この操作は、 [セットアップウィザード](set-up.md) で行うか、 [ユーザーにライセンスを割り当てる](../admin/manage/assign-licenses-to-users.md)ことができます。
    
### <a name="2-prepare-mobile-devices"></a>2: モバイルデバイスの準備

「Office アプリをデバイスにインストールする」および「Microsoft 365 for business で保護されていることを確認する」の「 [microsoft 365 用のモバイルデバイスのセットアップ](set-up-mobile-devices.md) 」の手順に従います。 
  
### <a name="3-prepare-pcs"></a>3: Pc の準備

管理者は、 [Windows 自動操縦](add-autopilot-devices-and-profile.md)を使用して、新しい Windows 10 pc の設定を事前に選択できます。 ユーザーは、このトピックの手順に従って、既存または新しい Windows 10 デバイスをセットアップできます。「 [Microsoft 365 for business ユーザーの Windows pc をセットアップ](set-up-windows-devices.md)する」。 既存のデバイスの場合、ユーザーは **オプション**で [ファイルを OneDrive for business に移動](move-files-to-onedrive.md)することができます。 サードパーティ製のツールを使用して、Windows プロファイルに関連付けられているファイルを OneDrive に移動することもできます。
  
組織がオンプレミスの Windows Server Active Directory を使用している場合は、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持しながら、Microsoft 365 for business をセットアップして、Windows 10 デバイスを保護することができます。 「ドメインに参加している Windows 10 デバイスを有効にする」の手順に従っ [て、Microsoft 365 for business で管理される](manage-windows-devices.md) ように設定します。 この方法を使用することをお勧めします。この状態のデバイスは、 **ハイブリッド AZURE AD に参加**しているデバイスと呼ばれます。 
  
オンプレミスのリソース (ファイル共有やプリンターなど) が含まれているローカルの Active Directory を保持する場合は、「 [Microsoft 365 for business の AZURE ad に参加しているデバイスからオンプレミスのリソースにアクセスする」](access-resources.md)の手順に従って、 **azure ad に参加**しているデバイスにこれらのリソースへのアクセスを許可できます。
  
  
## <a name="contact-support"></a>サポートに連絡

 **サポートに連絡する場合:**
  
- パートナーにお問い合わせください。
    
- Microsoft 365 for business 管理者は、カスタマーサポートチームにアクセスできます。一般 **[法人向け製品サポートへのお問い合わせ-管理者向けヘルプ](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)**
    
## <a name="see-also"></a>関連項目

[Microsoft 365 for business のドキュメントとリソース](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
Microsoft [365 for](manage.md)Business[から microsoft 365 への移行](migrate-to-microsoft-365-business.md)を管理する

[一般法人向け Microsoft 365 のトレーニング ビデオ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
