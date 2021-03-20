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
description: ビジネス向け Microsoft 365、セットアップ方法、ユーザーのデバイスと PC を準備して、Microsoft 365 でビジネス向け保護を行う方法について説明します。
ms.openlocfilehash: 9430dc7aa637be3fdb833150b83e96caacc82170
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912964"
---
# <a name="get-started-with-microsoft-365-for-business"></a>Microsoft 365 for business の使用を開始する

## <a name="what-is-microsoft-365-for-business"></a>Microsoft 365 for business とは

Microsoft 365 for business は、Outlook、Word、Excel、その他の Office 製品などのビジネス生産性とコラボレーション ツールの包括的なセットであり、常に最新の機能を備えています。 管理が簡単なエンタープライズ レベルのセキュリティを使用して、すべての iOS、Android、および Windows 10 デバイスで作業ファイルを保護できます。

Microsoft 365 for business の概要については、このビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 for business は、最大 300 ライセンスを使用することを意図しています。 ライセンスの追加が必要な場合は、[Microsoft 365 Enterprise](../enterprise/index.yml) のドキュメントで詳細を参照してください。 
  
## <a name="get-microsoft-365-for-business"></a>ビジネス向け Microsoft 365 を取得する

- パートナーが存在する場合、Microsoft 365 for business: Get [Microsoft 365 for business from Microsoft Partner Center](get-microsoft-365-business.md).
    
- パートナーがいないので、Microsoft 365 for business を取得する場合は、ここで [購入できます](https://www.microsoft.com/microsoft-365/business)。
    
## <a name="set-up-microsoft-365-for-business"></a>一般法人向け Microsoft 365 をセットアップする

 **Microsoft 365 for business Suite のセットアップの概要**
  
次の図は、管理者が Microsoft 365 for business をセットアップする方法を示しています。 また、ビジネス向け Microsoft 365 用 Windows PC を準備する手順も説明します。 Windows AutoPilot を使用して、Microsoft 365 管理センターに新しい [デバイスを追加することもできます](add-autopilot-devices-and-profile.md)。 AutoPilot を使用すると、ユーザーが Microsoft 365 でビジネス資格情報を使用してサインインするとすぐに、新しいデバイスをセットアップして事前構成できます。
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Microsoft 365 for business セットアップの概要については、このビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: ビジネス向け Microsoft 365 をセットアップする (管理者)

グローバル管理者資格情報 [を使用して Microsoft 365](https://portal.office.com/adminportal/home) 管理センターにサインインし、次の手順を実行して Microsoft 365 for business をセットアップします。 
  
1. [Microsoft 365 for business を使用してデバイス上のデータを保護するための前提条件](pre-requisites-for-data-protection.md)
    
    最初に前提条件を読んで、デバイスが Microsoft 365 for business の準備ができていることを確認します。
    
2. [セットアップ ウィザードを使用して Microsoft 365 for business をセットアップする](set-up.md)
    
    ローカルの **Active Directory** からクラウドに完全に移行する場合は、Microsoft 365 管理センターに移動し、セットアップ ウィザードを使用して手動でユーザーを追加するか、Azure AD Connect と 1 回の同期を行うことができます。 これを行うには 2 つの方法があります。 
    
    - Exchange 2010、Exchange 2013、または Exchange 2016 サーバーがある場合は、最小限のハイブリッドを使用して Exchange メールボックスを [Microsoft 365](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)にすばやく移行できます。 最小限のハイブリッド手順には、Azure ADへのユーザーの 1 回の同期、およびオンプレミスからクラウドへの電子メールの移行が含まれます。 電子メールの移行が完了すると、このメソッドを使用すると、ディレクトリ同期が自動的に無効になります。
    
    - ディレクトリ同期ウィザードを使用して、ユーザーをクラウドに同期します。 「Microsoft [365](../enterprise/set-up-directory-synchronization.md) のディレクトリ同期をセットアップする」の手順に従って、このプロセスを完了します。 ユーザーをクラウドに同期した後 [、Microsoft 365](../enterprise/turn-off-directory-synchronization.md)のディレクトリ同期をオフにする必要があります。
    
    また、この方法で追加された各ユーザーに、ビジネス向け Microsoft 365 のライセンスを提供する必要があります。 これは、セットアップ ウィザードで [実行するか、](set-up.md) ユーザーにライセンスを [割り当てできます](../admin/manage/assign-licenses-to-users.md)。
    
### <a name="2-prepare-mobile-devices"></a>2: モバイル デバイスを準備する

「ビジネス ユーザー向け Microsoft 365 用モバイル デバイスをセットアップして、Office アプリをデバイスにインストールし、ビジネス向け [Microsoft 365](set-up-mobile-devices.md) で保護されている」の手順に従います。 
  
### <a name="3-prepare-pcs"></a>3: PC の準備

管理者は、Windows AutoPilot を使用して、新しい Windows 10 PC の設定 [を事前に選択できます](add-autopilot-devices-and-profile.md)。 ユーザーは、このトピックの「ビジネス ユーザー向け [Microsoft 365 用 Windows PC](set-up-windows-devices.md)のセットアップ」の手順に従って、既存または新しい Windows 10 デバイスをセットアップできます。 既存のデバイスの場合、ユーザーは必要に **応** じて [OneDrive for Business にファイルを移動できます](move-files-to-onedrive.md)。 また、サード パーティ製のツールを使用して、Windows プロファイルに関連付けられているファイルを OneDrive に移動することもできます。
  
組織でオンプレミスの Windows Server Active Directory を使用している場合は、Microsoft 365 for business をセットアップして Windows 10 デバイスを保護しながら、ローカル認証を必要とするオンプレミス リソースへのアクセスを維持できます。 「ドメインに参加している Windows 10 デバイスを [Microsoft 365 for business](manage-windows-devices.md) で管理してこれを設定する」の手順に従います。 このメソッドが推奨され、この状態のデバイスはハイブリッド Azure と呼ばAD **デバイスです**。 
  
一部のオンプレミス リソース (ファイル共有やプリンターなど) を含むローカル Active Directory を保持する場合は、次の手順に従って **、Azure AD** に参加しているデバイスにこれらのリソースへのアクセス権を与えることができます。ビジネス向け [Microsoft 365](access-resources.md)の Azure AD に参加しているデバイスからオンプレミス リソースにアクセスします。
  
  
## <a name="contact-support"></a>サポートに連絡する

 **サポートに連絡する場合:**
  
- パートナーにお問い合わせください。
    
- Microsoft 365 for business admin として、カスタマー サポート チームにアクセスできます。ビジネス製品のサポートに問い合わせ **[- 管理者ヘルプ](../admin/contact-support-for-business-products.md)**
    
## <a name="see-also"></a>関連項目

[Microsoft 365 for business のドキュメントとリソース](./index.yml)
  
[ビジネス向け Microsoft 365 の管理](manage.md)[ビジネス向け Microsoft 365 への移行](migrate-to-microsoft-365-business.md)

[一般法人向け Microsoft 365 のトレーニング ビデオ](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)