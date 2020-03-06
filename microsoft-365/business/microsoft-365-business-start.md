---
title: Microsoft 365 Business を使い始める
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
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Microsoft 365 Business、セットアップ方法、およびユーザーのデバイスと Pc を準備して Microsoft 365 Business で保護されるようにする方法について説明します。
ms.openlocfilehash: f6fd73762c0b57777c19d32886f758875e2e7e6a
ms.sourcegitcommit: 41c0bc5cf50f4ca63b4286d1ea0f58ab82984b7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2020
ms.locfileid: "42547733"
---
# <a name="get-started-with-microsoft-365-business"></a>Microsoft 365 Business を使い始める

## <a name="what-is-microsoft-365-business"></a>Microsoft 365 Business とは

Microsoft 365 Business は、Outlook、Word、Excel、その他の Office 製品など、常に最新の状態になっているビジネス生産性とコラボレーションツールの包括的なセットです。 管理が簡単なエンタープライズレベルのセキュリティを使用して、すべての iOS、Android、Windows 10 デバイス上の作業ファイルを保護することができます。

Microsoft 365 Business の簡単な概要については、このビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365 Business は、最大300のライセンスを想定しています。 その他のライセンスが必要な場合は、「 [Microsoft 365 Enterprise](https://go.microsoft.com/fwlink/p/?linkid=860986)ドキュメント」を参照してください。 
  
## <a name="get-microsoft-365-business"></a>Microsoft 365 Business を入手する

- パートナーがいる場合は、microsoft 365 Business: microsoft[パートナーセンターから microsoft 365 business を取得](get-microsoft-365-business.md)することになります。
    
- パートナーを持っておらず、Microsoft 365 Business を入手したい場合は、[ここで購入](https://www.microsoft.com/microsoft-365/business)できます。
    
## <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business のセットアップ

 **Microsoft 365 Business Suite のセットアップの概要**
  
次の図では、管理者が Microsoft 365 Business をセットアップする方法について説明します。 また、Microsoft 365 Business 用に Windows Pc を準備する手順についても説明します。 [Windows 自動操縦](add-autopilot-devices-and-profile.md)を使用して、Microsoft 365 Business 管理センターで新しいデバイスを追加することもできます。 自動操縦を使用して、ユーザーが Microsoft 365 のビジネス資格情報を使用してサインインできるようになるとすぐに、新しいデバイスをセットアップして事前構成することができます。
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

Microsoft 365 Business のセットアップの概要については、このビデオをご覧ください。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

このビデオが役に立った場合には、「[complete training series for small businesses and those new to Microsoft 365 (小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ)](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)」をご覧ください。

  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: Microsoft 365 Business をセットアップする (管理者)

グローバル管理者の資格情報を使用して[microsoft 365 business 管理センター](https://portal.office.com/adminportal/home)にサインインし、次の手順を実行して Microsoft 365 Business をセットアップします。 
  
1. [Microsoft 365 Business を使用してデバイス上のデータを保護するための前提条件](pre-requisites-for-data-protection.md)
    
    最初に前提条件を読んで、デバイスの Microsoft 365 Business の準備が整っていることを確認してください。
    
2. [セットアップウィザードを使用して Microsoft 365 Business をセットアップする](set-up.md)
    
    **ローカルの Active Directory からクラウドに完全に移動**する場合は、Microsoft 365 Business 管理センターに移動し、セットアップウィザードを使用してユーザーを手動で追加するか、または Azure AD Connect を使用して1回限りの同期を行うことができます。 これを行うには 2 つの方法があります。 
    
    - Exchange 2010、Exchange 2013、または Exchange 2016 サーバーもある場合は、最小限の[ハイブリッドを使用して、exchange メールボックスを Office 365 にすばやく移行](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef)できます。 最低限のハイブリッド手順には、Azure AD へのユーザーの1回限りの同期と、オンプレミスからクラウドへの電子メールの移行が含まれます。 メールの移行が完了した後、この方法を使用すると、ディレクトリ同期は自動的に無効になります。
    
    - Office 365 ディレクトリ同期ウィザードを使用して、ユーザーをクラウドに同期させます。 「[Office 365 のディレクトリ同期をセットアップする](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)」の手順に従って、このプロセスを完了します。 ユーザーをクラウドに同期させた後、 [Office 365 のディレクトリ同期を無効](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d)にする必要があります。
    
    また、このように追加された各ユーザーに、Microsoft 365 Business のライセンスを付与する必要があります。 この操作は、[セットアップウィザード](set-up.md)で行うことができます。または、 [Office 365 for business のユーザーにライセンスを割り当てる](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC)ことができます。
    
### <a name="2-prepare-mobile-devices"></a>2: モバイルデバイスの準備

「 [Microsoft 365 business ユーザー向けのモバイルデバイスのセットアップ](set-up-mobile-devices.md)」の手順に従って、Office アプリをデバイスにインストールし、Microsoft 365 business で保護されていることを確認します。 
  
### <a name="3-prepare-pcs"></a>3: Pc の準備

管理者は、 [Windows 自動操縦](add-autopilot-devices-and-profile.md)を使用して、新しい Windows 10 pc の設定を事前に選択できます。 ユーザーは、このトピックの手順に従って、既存または新しい Windows 10 デバイスをセットアップできます。 [Microsoft 365 Business ユーザーの Windows pc をセットアップ](set-up-windows-devices.md)します。 既存のデバイスの場合、ユーザーは**オプション**で[ファイルを OneDrive for business に移動](move-files-to-onedrive.md)することができます。 サードパーティ製のツールを使用して、Windows プロファイルに関連付けられているファイルを OneDrive に移動することもできます。
  
組織がオンプレミスの Windows Server Active Directory を使用している場合は、Windows 10 のデバイスを保護するように Microsoft 365 Business をセットアップし、ローカル認証を必要とするオンプレミスのリソースへのアクセスを維持することができます。 「[ドメインに参加している Windows 10 デバイスが Microsoft 365 Business で管理される](manage-windows-devices.md)ようにする」の手順に従って、これを設定します。 この方法を使用することをお勧めします。この状態のデバイスは、**ハイブリッド AZURE AD に参加**しているデバイスと呼ばれます。 
  
オンプレミスのリソース (ファイル共有やプリンターなど) を含むローカルの Active Directory を保持する場合は、「 [Microsoft 365 Business の AZURE ad に参加しているデバイスからオンプレミスのリソースにアクセスする」](access-resources.md)の手順に従って、 **azure ad に参加**しているデバイスにこれらのリソースへのアクセス権を与えることができます。
  
  
## <a name="contact-support"></a>サポートに連絡

 **サポートに連絡する場合:**
  
- パートナーにお問い合わせください。
    
- Microsoft 365 Business 管理者は、カスタマーサポートチームにアクセスできます。 **[ビジネス製品のサポートに問い合わせる-管理者向けヘルプ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)**
    
## <a name="see-also"></a>関連項目

[Microsoft 365 Business のドキュメントとリソース](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
Microsoft [365 business](manage.md)[移行を microsoft 365 business に管理する](migrate-to-microsoft-365-business.md)

[Microsoft 365 Business のトレーニング ビデオ](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816) 
