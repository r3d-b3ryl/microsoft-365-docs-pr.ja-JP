---
title: セットアップ ウィザードを使用して Microsoft 365 Business をセットアップする
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 4 つの手順を実行して Microsoft 365 のビジネスを設定する方法について説明します。
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869005"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>セットアップ ウィザードを使用して Microsoft 365 Business をセットアップする

1 ~ 4 の次の手順を完了します。
  
### <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business をセットアップする

オンプレミスの Active Directory がない場合は、Microsoft 365 のビジネスをセットアップする方法に関するビデオを視聴するには。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
セットアップ手順には、ローカルの Active directory の設定に関する情報が含まれます。ドメインに参加しているデバイスへのアクセスを続行する場合は、次の記事を参照するには、有効にする別の方法を 2 つのと、セットアップ ウィザードを実行する前に手順を完了します。
  
- [Microsoft 365 のビジネスを管理する Windows 10 のドメインに参加しているデバイスを有効にします。](manage-windows-devices.md)
    
    -これは、推奨される方法です。
    
- [アクセスは、オンプレミス マイクロソフト 365 ビジネスで Azure AD に参加しているデバイスからのリソース](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>サインインの手順 1: 個人用に設定します。

1. グローバル管理者の資格情報を使用して、[Microsoft 365 Business](https://portal.microsoft.com) にサインインします。[ **管理者**] タイルを選び、管理センターに移動します。 
    
2. 管理センターで [ **セットアップの開始**] (状態によっては、[ **セットアップの続行**] が代わりに表示される場合があります) を選び、ウィザードを開始します。 
    
3. 使用するドメイン名 (Contoso.com など) を入力します。
    
    たとえば Azure の AD 接続を使用中に確認した場合でも、ドメインを入力してください。自分のドメインを確認するのには Azure AD 接続を使用する場合、次の 2 つの手順は適用されません。
    
4. [Office 365 のすべての DNS ホスティング プロバイダーを作成する DNS レコード](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166)のドメインを所有することを検証するにウィザードの手順に従います。 
    
    例のビデオを表示することができます[ビデオ: 新しい管理センターのセットアップの Office 365](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)。このビデオに 365 ビジネスのマイクロソフトのデータ保護の手順が含まれていないことに注意してください。
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>手順 2: ユーザーを追加し、ライセンスを割り当てる

1. ここではユーザーを追加することも、管理センターで[後からユーザーを追加](add-users-m365b.md)することもできます。 
    
    追加するユーザーには、自動的に Microsoft 365 Business ライセンスが割り当てられます。
    
2. Microsoft 365 Business のサブスクリプションに既存ユーザーがいる場合 (たとえば、Azure AD Connect を使用した場合)、今すぐこれらのユーザーにライセンスを割り当てるオプションが表示されます。続行して、これらのユーザーにもライセンスを追加します。
    
3. 追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。それらを印刷、メール、またはダウンロードできます。
    
4. 移行のメール メッセージをスキップして、[ **メール メッセージの移行**] ページで [ **次へ**] を選びます。 
    
    別の電子メール プロバイダーからの移動は、後でデータをコピーする場合、[移行の電子メールと連絡先を Office 365 に](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)することができます。
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>手順 3: 自分のドメインを接続します。

> [!NOTE]
> .Onmicrosoft のドメインを使用することを選択した場合、または AD の Azure の接続を使用する場合は、この手順は表示されません。 
  
サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。
  
1. セットアップ ウィザードは、通常、レジストラーを検出し、レジストラーの web サイトにある NS レコードを更新するための詳細な手順へのリンクを使用します。インストールされていない場合、[任意のドメイン レジストラーに Office 365 をセットアップするネーム サーバーを変更](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)します。
    
2. メールとその他のサービスが自動的に設定されます。
    
### <a name="step-4-manage-devices-and-work-files"></a>手順 4: デバイスを管理し、作業ファイル

1. **、モバイル デバイスの作業ファイルを保護する**には、ページは、**上**に**デバイスが紛失または盗難に遭ったときの保護の作業ファイル**と設定の**管理ユーザーがモバイル デバイス上の Office ファイルにアクセスする方法**の両方を設定します。各サブ設定で各設定の横の下向きの矢印をクリックしてアクセスすることもできます。
  
  しだい、iOS および Android デバイスで保護するは今すぐすべての作業ファイルのライセンスを受けたユーザーの[Office アプリケーションのインストール](set-up-mobile-devices.md)(および Microsoft 365 ビジネス資格情報で認証)。 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. **Windows 10 の設定のデバイスの構成**] ページで [ **Windows 10 デバイスをセキュリティで保護された**設定を**オン**に設定します。
  
   各サブ設定の横にある山形の記号をクリックしてアクセスすることもできます。
  
3. **10 の Windows デバイス上の Office のインストール**設定を設定すると、 **[はい]** すべてのユーザー、コンピューターの Windows 10 があり、しないか、既存の Office をインストールする場合] または [Office のインストールを実行] をクリックします。大文字と小文字でない場合は、 **「いいえ**」をこのオプションを設定します。ユーザーのコンピューターを準備した後は管理センターから後で[自動的にインストールする Office](auto-install-or-uninstall-office.md)をできます。手順については、 [Office クライアントのインストールの準備](prepare-for-office-client-deployment.md)を参照してください。
  
    10 の Windows デバイス上のライセンスを受けたユーザーの作業ファイルがすぐに、投影する Microsoft 365 ビジネス Azure AD ドメインまたは Microsoft 365 に同時に参加するときに[新しいコンピューターに Windows の 10 をインストールする](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)に[、10 の Windows デバイスへの参加](set-up-windows-devices.md)をビジネス Azure AD ドメインです。 
  
4. [**次へ**] をクリックし、セットアップを終了します。 
  
    くださいフィードバックを送信我々 エクスペリエンスを向上させるためには、この手順で。
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>その他のセキュリティ設定

だけでなく、セキュリティとコンプライアンスの設定のセットアップ ウィザードで、次の追加設定を設定することも。
  
- 安全でない添付ファイルからの保護を設定します。**脅威保護の詳細**(ATP) は、悪意のあるコンテンツを識別し、フィッシング詐欺や ransomware のウイルス感染から保護するため、安全でない添付ファイルの配信をブロックします。添付ファイルの保護を有効にするのには[Office 365 ATP の安全な添付ファイルのポリシー設定](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)を参照してください。
    
- ユーザーが悪意のあるリンクをクリックしたときは、環境を保護します。ATP は、時に、ユーザーをクリックしてメール内のリンクを検証します。リンクが安全でない場合は、ユーザーがサイトにアクセスしないように警告またはサイトがブロックされたことを通知します。これにより、フィッシング詐欺から保護します。[Office 365 の ATP の安全なリンクのポリシーを設定](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)または[ポリシーを Office 365 の ATP の安全なリンクを設定](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)します。
    
- **保持訴訟**でユーザーのメールボックスの全体を配置することで削除済みアイテムを含むすべてのメールボックスの内容を保持できます。手順については、次を参照してください。 
- [Exchange Online Archiving の電子メールの保存期間を設定](security-features.md#set-up-email-retention-with-exchange-online-archiving)します。
    
- 設定 **・ リテンション ・ ポリシー**をカスタマイズしたなどの一定の時間を保持するか、保存期間の終了時にコンテンツを完全に削除します。カスタマイズされた保存ポリシーでは、セキュリティとコンプライアンス部門、**データ ・ ガバナンス**に移動させることができます\>**の保存**、し、ウィザードの手順です。詳細については、[保存ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)を参照してください。
    
## <a name="next-steps"></a>次の手順

ライセンスがあるユーザーは、次の手順でデバイスをセットアップします。<br/> 「[Microsoft 365 Business ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md)」と「[Microsoft 365 Business ユーザーのモバイル デバイスをセットアップする](set-up-mobile-devices.md)」を参照してください。 <br/>デバイスとアプリの保護ポリシーを設定する方法、およびユーザーのデバイスからデータを削除する方法に関する記事へのリンクについては、「[Microsoft 365 Business を管理する](manage.md)」を参照してください。 
  


