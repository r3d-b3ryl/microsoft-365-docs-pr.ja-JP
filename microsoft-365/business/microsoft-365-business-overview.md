---
title: Microsoft 365 Business を使い始める
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.date: 9/20/2018
ms.audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 496e690b-b75d-4ff5-bf34-cc32905d0364
description: Microsoft 365 のビジネスを設定するを説明します。
ms.openlocfilehash: ee15ffa98de032d7936d950124cdf772335949bd
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869401"
---
# <a name="get-started-with-microsoft-365-business"></a>Microsoft 365 Business を使い始める

## <a name="what-is-microsoft-365-business"></a>Microsoft 365 Business とは

Microsoft 365 Business は、ビジネス生産性と共同作業ツールの包括的なセットです。これには、常に最新の状態に保たれた Outlook、Word、Excel、およびその他の Office 製品が含まれます。iOS、Android、Windows 10 のすべてのデバイス上の作業ファイルを、管理が容易なエンタープライズ レベルのセキュリティで保護することができます。
  
Microsoft 365 のビジネスは、最大で 300 分のライセンスでは、多くのライセンスが必要な場合、詳細については[マイクロソフトの 365 の企業](https://go.microsoft.com/fwlink/p/?linkid=860986)内のドキュメントを参照してください。 
  
## <a name="get-microsoft-365-business"></a>Microsoft 365 Business を入手する

- パートナーがいる場合、パートナーは Microsoft 365 Business を入手します: [Microsoft パートナー センターから Microsoft 365 Business を購入する](get-microsoft-365-business.md)。
    
- しないしている場合、パートナー Microsoft 365 のビジネスを取得する、[ここでそれを購入](https://www.microsoft.com/en-us/microsoft-365/business)することができます。
    
## <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business をセットアップする

 **365 ビジネス スイートの Microsoft の概要の設定**
  
次の図では、管理者が Microsoft 365 のビジネスをどのように設定する方法について説明します。365 ビジネスのマイクロソフトの Windows Pc を準備する手順についても説明します。[Windows の自動操縦](add-autopilot-devices-and-profile.md)で Microsoft 365 ビジネス管理センターに新しいデバイスを追加することも。設定し、事前に構成する、新しいデバイスの準備をして生産性 Microsoft 365 のビジネス情報を使用してユーザーに署名するとすぐに自動操縦装置を使用できます。
  
![A diagram that shows the setup and management flow for admins, and also for a user](media/249f81fc-7e79-44c7-8425-3a0b7b651c3b.png)
  
### <a name="1-set-up-microsoft-365-business-admin"></a>1: マイクロソフト 365 ビジネス (管理者) を設定します

グローバル管理者の資格情報で [Microsoft 365 Business 管理センター](https://portal.office.com/adminportal/home)にサインインし、次の手順を完了して Microsoft 365 Business をセットアップします。 
  
1. [Microsoft 365 Business でデバイス上のデータを保護するための前提条件](pre-requisites-for-data-protection.md)
    
    最初に前提条件を読み、デバイスが Microsoft 365 Business の前提条件を満たしていることを確認します。
    
2. [セットアップ ウィザードを使用して Microsoft 365 Business をセットアップする](set-up.md)
    
    か、ユーザーを追加できます、手動で Microsoft 365 ビジネス管理センターで、セットアップ ウィザードを使用して**クラウドに移行する場合は、ローカル Active Directory から完全に移動**する場合は、または、Azure AD 接続と 1 回だけの同期を行うことができます。これを行う 2 つの方法があります。 
    
  - Exchange 2010、Exchange 2013 年または 2016 の Exchange サーバーがあるも、[簡単に Office 365 に Exchange メールボックスを移行するのには最低限のハイブリッドを使用](https://support.office.com/article/fdecceed-0702-4af3-85be-f2a0013937ef)することができます。ハイブリッドを最小限に抑える手順 Azure AD ユーザーの 1 回だけ同期を含めるだけではなく、電子メールのオンプレミスからクラウドへの移行。電子メールの移行が完了したら、ディレクトリ同期を自動的に無効になってこのメソッドを使用する場合。
    
  - Office 365 のディレクトリ同期のウィザードを使用して、ユーザーをクラウドに同期させます。「[Office 365 のディレクトリ同期をセットアップする](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)」の手順に従って、このプロセスを完了します。ユーザーをクラウドに同期させた後で、[ディレクトリの同期をオフにする](https://support.office.com/article/ee5f861e-bd48-4267-83d1-a4ead4b4a00d)必要があります。
    
    Microsoft 365 のビジネスをこのように、ライセンスを追加した各ユーザーに提供する必要があります。これは、[セットアップ ウィザード](set-up.md)で、または[ビジネスのための Office 365 のユーザーにライセンスを割り当てる](https://support.office.com/article/997596B5-4173-4627-B915-36ABAC6786DC)で行うことができます。
    
### <a name="2-prepare-mobile-devices"></a>2: モバイル デバイスの準備

デバイスと Microsoft 365 ビジネスによって保護されていることを確認する Office アプリケーションをインストールするのには[Microsoft 365 ビジネス ユーザー向けのモバイル デバイスの設定](set-up-mobile-devices.md)を手順を実行します。 
  
### <a name="3-prepare-pcs"></a>3: Pc を準備します。

管理者は、 [Windows の自動操縦](add-autopilot-devices-and-profile.md)を使用して新しいデバイス 10 の Pc を Windows の設定を事前選択できます。ユーザーは、このトピックの手順を実行して、既存または新規の Windows 10 デバイスを設定できます。 [Microsoft 365 ビジネス ユーザー向けの Windows Pc を設定](set-up-windows-devices.md)します。既存のデバイスのユーザーことも**[ビジネスの OneDrive にファイルを移動](move-files-to-onedrive.md)** できます。OneDrive に Windows のプロファイルに関連付けられているファイルを移動するのにはサードパーティ製のツールも使用できます。
  
組織は、Windows サーバーの Active Directory の設置型を使用している場合は、ローカルの認証を必要とする設置型のリソースへのアクセスを維持しながら、10 の Windows のデバイスを保護するために Microsoft 365 のビジネスを設定できます。[Microsoft 365 のビジネスを管理する Windows 10 のドメインに参加しているデバイスを有効にする](manage-windows-devices.md)設定の手順に従います。これは推奨される方法であり、この状態のデバイスは、**ハイブリッド Azure AD には、デバイスが参加するいる**と呼ばれます。 
  
ローカルに保持する場合は、いくつか含まれている Active Directory の設置型リソース (ファイル共有やプリンターなど)、以下の手順でのこれらのリソースに、 **Azure の AD に参加しているデバイス**のアクセスを与えることができます:[アクセス、オンプレミス リソースから、Microsoft 365 のビジネスで、azure の AD に参加しているデバイス](access-resources.md)。
  
10 Pc の Windows をセットアップした後、デバイスに[自動的に Office をインストール](auto-install-or-uninstall-office.md)することができます。 
  
## <a name="contact-support"></a>サポートに連絡

 **サポートに連絡する場合:**
  
- パートナーにお問い合わせください。
    
- 、Microsoft 365 業務管理者として、カスタマー サポート チーム、**[のビジネス製品の管理のヘルプのお問い合わせ](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)へのアクセスがあります。**
    

