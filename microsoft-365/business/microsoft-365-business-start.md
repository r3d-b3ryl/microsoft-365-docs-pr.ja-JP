---
title: ビジネス向けMicrosoft 365を開始する
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: ビジネス向けMicrosoft 365、セットアップ方法、ユーザーのデバイスと PC を準備して、ユーザーがビジネス向けデバイスで保護Microsoft 365します。
ms.openlocfilehash: 2ab0079da7a8f30d481cdb3d3dc6d165b4a19e99
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339292"
---
# <a name="get-started-with-microsoft-365-for-business"></a>ビジネス向けMicrosoft 365を開始する

## <a name="what-is-microsoft-365-for-business"></a>ビジネスMicrosoft 365について

Microsoft 365は、常に最新の Outlook、Word、Excel、その他の Office 製品などのビジネス生産性とコラボレーション ツールの包括的なセットです。 管理が簡単なエンタープライズ レベルのセキュリティを使用して、すべての iOS、Android、Windows 10 デバイスで作業ファイルを保護できます。

## <a name="watch-what-is-microsoft-365-business-premium"></a>ご覧ください: Microsoft 365 Business Premium とは

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2mhaA] 
  
Microsoft 365は、最大 300 ライセンスを使用します。 ライセンスの追加が必要な場合は、[Microsoft 365 Enterprise](../enterprise/index.yml) のドキュメントで詳細を参照してください。 
  
## <a name="get-microsoft-365-for-business"></a>ビジネスMicrosoft 365を取得する

- パートナーが存在する場合は、ビジネス向Microsoft 365 Microsoft パートナー センターからビジネスMicrosoft 365を[取得](get-microsoft-365-business.md)します。
    
- パートナーがいない場合は、ビジネスMicrosoft 365取得する場合は、ここで[購入できます](https://www.microsoft.com/microsoft-365/business)。
    
## <a name="set-up-microsoft-365-for-business"></a>一般法人向け Microsoft 365 をセットアップする

 **ビジネス スイートMicrosoft 365設定の概要**
  
次の図は、管理者がビジネス向けMicrosoft 365設定する方法を示しています。 また、ビジネス向け PC の準備Windows手順Microsoft 365説明します。 また、AutoPilot を使用して、Microsoft 365 管理センターデバイスWindows[追加することもできます](add-autopilot-devices-and-profile.md)。 AutoPilot を使用すると、新しいデバイスをセットアップおよび事前構成して、ユーザーがビジネス資格情報用の Microsoft 365 を使用してサインインするとすぐに、生産性の高い使用を実現できます。
  
![A diagram that shows the setup and management flow for admins, and also for a user](../media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)

## <a name="watch-set-up-microsoft-365-business"></a>ウォッチ: ビジネスをMicrosoft 365する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FYSM] 

このビデオがお役に立った場合には、「[小規模企業および Microsoft 365 を初めて使用する企業向けのトレーニング シリーズ](../business-video/index.yml)」をご覧ください。

  
### <a name="1-set-up-microsoft-365-for-business-admin"></a>1: ビジネス向Microsoft 365を設定する (管理者)

グローバル管理者の[資格情報Microsoft 365 管理センター](https://admin.microsoft.com/adminportal/home)サインインして、次の手順を実行してビジネス向Microsoft 365設定します。 
  
1. [ビジネス向けデバイスでデータを保護するためのMicrosoft 365前提条件](pre-requisites-for-data-protection.md)
    
    最初に前提条件を読んで、デバイスがビジネス向けMicrosoft 365確認してください。
    
2. [セットアップ ウィザードを使用してビジネス向けMicrosoft 365セットアップする](set-up.md)
    
    ローカル **の Active Directory** からクラウドに完全に移動する場合は、Microsoft 365 管理センター に移動してセットアップ ウィザードを使用してユーザーを手動で追加するか、Azure AD Connect と 1 回の同期を行うことができます。 これを行うには次に示す 2 つの方法があります。 
    
    - Exchange 2010、Exchange 2013、または Exchange 2016 サーバーがある場合は、最小限のハイブリッドを使用して Exchange メールボックスをすばやく Microsoft 365 に[移行できます](/Exchange/mailbox-migration/use-minimal-hybrid-to-quickly-migrate)。 最小限のハイブリッド手順には、Azure ADへのユーザーの 1 回の同期、およびオンプレミスからクラウドへの電子メールの移行が含まれます。 電子メールの移行が完了すると、このメソッドを使用すると、ディレクトリ同期が自動的に無効になります。
    
    - ディレクトリ同期ウィザードを使用して、ユーザーをクラウドに同期します。 「ディレクトリ同期のセットアップ[」の手順に従って、Microsoft 365](../enterprise/set-up-directory-synchronization.md)を完了します。 ユーザーをクラウドに同期した後、ユーザーのディレクトリ同期をオフ[にする](../enterprise/turn-off-directory-synchronization.md)必要Microsoft 365。
    
    また、この方法で追加された各ユーザーに、ビジネス向けライセンスを提供Microsoft 365があります。 これは、セットアップ ウィザードで [実行するか、](set-up.md) ユーザーにライセンスを [割り当てできます](../admin/manage/assign-licenses-to-users.md)。
    
### <a name="2-prepare-mobile-devices"></a>2: モバイル デバイスを準備する

「Microsoft 365 用[](set-up-mobile-devices.md)にモバイル デバイスをセットアップして、Office アプリをデバイスにインストールし、ビジネス向け Microsoft 365 で保護Microsoft 365します。 
  
### <a name="3-prepare-pcs"></a>3: PC の準備

管理者は、AutoPilot を使用して新Windows 10 PC の[Windows選択できます](add-autopilot-devices-and-profile.md)。 ユーザーは、このトピックの手順に従って、既存Windows 10または新しい Windows 10 デバイスをセットアップできます。ビジネス ユーザー向け Windows PC Microsoft 365[を設定します](set-up-windows-devices.md)。 既存のデバイスの場合、ユーザー **は必要** に応じて [ファイルをファイルに移動OneDrive for Business。](move-files-to-onedrive.md) また、サード パーティ製のツールを使用して、プロファイルに関連付けられているファイルWindowsに移動OneDrive。
  
組織で Windows Server Active Directory オンプレミスを使用している場合は、Windows 10 デバイスを保護しながら、ローカル認証を必要とするオンプレミス リソースへのアクセスを維持しながら、Microsoft 365 をビジネス用にセットアップできます。 「ドメインに参加しているデバイスWindows 10を有効にする」の手順に従って、Microsoft 365[を](manage-windows-devices.md)設定します。 このメソッドが推奨され、この状態のデバイスはハイブリッド Azure と呼ばAD **デバイスです**。 
  
一部のオンプレミス リソース (ファイル共有やプリンターなど) を含むローカル Active Directory を保持する場合は、Azure AD に参加しているデバイスにこれらのリソースへのアクセス権を与えることができます。次の手順を実行します。ビジネス向け Microsoft 365 で [Azure](access-resources.md) **AD** に参加しているデバイスからオンプレミス リソースにアクセスします。
  
  
## <a name="contact-support"></a>サポートにお問い合せください

 **サポートに連絡する場合:**
  
- パートナーにお問い合わせください。
    
- ビジネス管理者Microsoft 365、カスタマー サポート チームにアクセスできます。ビジネス製品のサポートへの問い合わせ **[- 管理者ヘルプ](../business-video/get-help-support.md)**
    
## <a name="related-content"></a>関連コンテンツ

[Microsoft 365ドキュメントとリソースの詳細](./index.yml)(リンク ページ)\
[ビジネスMicrosoft 365管理](manage.md)(記事)\
[ビジネス向Microsoft 365に移行](migrate-to-microsoft-365-business.md)する (記事)\
[一般法人向け Microsoft 365 のトレーニング ビデオ](../business-video/index.yml) (リンク ページ)