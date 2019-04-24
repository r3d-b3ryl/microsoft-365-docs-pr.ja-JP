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
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 4つの手順を完了して Microsoft 365 Business をセットアップする方法について説明します。
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283921"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>セットアップ ウィザードを使用して Microsoft 365 Business をセットアップする

以下の手順1-4 を完了します。
  
### <a name="set-up-microsoft-365-business"></a>Microsoft 365 Business をセットアップする

オンプレミスの Active Directory がインストールされていない場合に Microsoft 365 Business をセットアップする方法についてのビデオをご覧ください。
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
セットアップ手順には、ローカルの Active Directory を含む設定に関する情報が含まれています。 ドメインに参加しているデバイスへのアクセスを継続する場合は、次に示す2つの異なる方法について以下の記事を読んで、セットアップウィザードを実行する前に手順を完了します。
  
- [Microsoft 365 Business で管理されるドメインに参加している Windows 10 デバイスを有効にする](manage-windows-devices.md)
    
    -これは推奨される方法です。
    
- [Microsoft 365 Business で Azure AD に参加しているデバイスからオンプレミスのリソースにアクセスする](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>手順 1: サインインをカスタマイズする

1. グローバル管理者の資格情報を使用して、[Microsoft 365 Business](https://portal.microsoft.com) にサインインします。[ **管理者**] タイルを選び、管理センターに移動します。 
    
2. 管理センターで [ **セットアップの開始**] (状態によっては、[ **セットアップの続行**] が代わりに表示される場合があります) を選び、ウィザードを開始します。 
    
3. 使用するドメイン名 (Contoso.com など) を入力します。
    
    続けて自分のドメインを入力します。Azure AD Connect などを使用している間にドメインを確認した場合でも入力します。 Azure AD Connect を使用してドメインを確認した場合、次の2つの手順は適用されません。
    
4. ウィザードの手順に従って、ドメインを所有していることを確認する[Office 365 用の任意の dns ホスティングプロバイダーで dns レコードを作成](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166)します。 
    
    ビデオの例については、[新しい管理センターで Office 365 をセットアップ](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8)するを参照してください。 このビデオには、Microsoft 365 Business のデータ保護手順は含まれていないことに注意してください。
    
    ![Screenshot of the Business Cloud Suite setup wizard.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>手順 2: ユーザーを追加してライセンスを割り当てる

1. ここではユーザーを追加することも、管理センターで[後からユーザーを追加](add-users-m365b.md)することもできます。 
    
    追加するユーザーには、自動的に Microsoft 365 Business ライセンスが割り当てられます。
    
2. Microsoft 365 Business のサブスクリプションに既存ユーザーがいる場合 (たとえば、Azure AD Connect を使用した場合)、今すぐこれらのユーザーにライセンスを割り当てるオプションが表示されます。続行して、これらのユーザーにもライセンスを追加します。
    
3. 追加した新しいユーザーと資格情報を共有するためのオプションも表示されます。それらを印刷、メール、またはダウンロードできます。
    
4. 移行のメール メッセージをスキップして、[ **メール メッセージの移行**] ページで [ **次へ**] を選びます。 
    
    別のメールプロバイダーから移行していて、後でデータをコピーする場合は、[メールと連絡先を Office 365 に移行](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e)できます。
    
    ![Screenshot of two new users added in the setup wizard](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>手順 3: ドメインを接続する

> [!NOTE]
> . onmicrosoft ドメインを使用するか、Azure AD Connect を使用することを選択した場合は、この手順は表示されません。 
  
サービスを設定するには、DNS ホストまたはドメイン レジストラーにあるレコードを更新する必要があります。
  
1. セットアップ ウィザードでは通常、ユーザーのレジストラーが検出され、レジストラーの Web サイトで NS レコードを更新するための詳しい操作手順へのリンクが表示されます。 含まれていない場合は、ネームサーバーを[変更して、任意のドメインレジストラーで Office 365](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)をセットアップします。
    
2. メールとその他のサービスが自動的に設定されます。
    
### <a name="step-4-manage-devices-and-work-files"></a>手順 4: デバイスと作業ファイルを管理する

1. [**モバイルデバイスの作業ファイルを保護**する] ページで、[**デバイスの紛失または盗難時に作業ファイルを保護**する] と [**ユーザーがモバイルデバイスの設定で Office ファイルにアクセスする方法**を**オン**にする方法を管理する] の両方を設定します。 各サブ設定にアクセスするには、各設定の横にある山かっこをクリックします。
  
  ユーザーが[Office アプリをインストール](set-up-mobile-devices.md)し、Microsoft 365 Business の資格情報を使用して認証を行うとすぐに、ライセンスが付与されたすべてのユーザーの作業ファイルが iOS および Android デバイスで保護されるようになります。 
  
  ![Screenshot of protect work files on your mobile devices page](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. [ **windows 10 デバイス構成の設定**] ページで、[**セキュリティで保護された windows 10 デバイス**の設定] を **[オン**] に設定します。
  
   また、各サブ設定にアクセスするには、その横の山形記号をクリックします。
  
3. すべてのユーザーが windows 10 台のコンピューターを持ち、既存の office インストールがない場合、またはクイック実行 office インストールを使用している場合は、[ **windows 10 デバイスに Office をインストール**する **] を [はい]** に設定します。 そうでない場合は、このオプションを [**いいえ**] に設定します。 ユーザーのコンピューターの準備が完了すると、後で管理センターから[Office を自動的にインストール](auto-install-or-uninstall-office.md)することができます。 手順については、「 [Office クライアントのインストールを準備する](prepare-for-office-client-deployment.md)」を参照してください。
  
    windows 10 デバイスのライセンスユーザーの作業ファイルは、windows 10 デバイスを microsoft 365 Business Azure AD ドメインに[参加](set-up-windows-devices.md)させるとすぐに、または microsoft 365 に同時に参加している間に[新しいコンピューターに windows 10 をインストール](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx)すると、直ちに投影されます。Business Azure AD ドメイン。 
  
4. [**次へ**] をクリックして、セットアップを終了します。 
  
    この手順でフィードバックをお寄せください。
  
    ![Screenshot of Prepare Windows 10 devices page](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>その他のセキュリティ設定

セットアップウィザードのセキュリティとコンプライアンスの設定に加えて、次の追加設定を設定することもできます。
  
- 安全でない添付ファイルに対する保護を設定します。 **Advanced Threat Protection**(ATP) 悪意のあるコンテンツを特定し、安全でない添付ファイルの配信をブロックすることで、フィッシング詐欺やランサムウェアによる感染に対する保護を促進します。 添付ファイル保護をアクティブにするには、「 [Office 365 ATP の安全な添付ファイルのポリシーを](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy)セットアップする」を参照してください。
    
- ユーザーが悪意のあるリンクをクリックしたときに環境を保護します。 ATP は、ユーザーがクリックしたときに電子メール内のリンクを調べます。 リンクが安全でない場合、ユーザーはサイトにアクセスしないように警告が出されるか、サイトがブロックされていることが通知されます。 これにより、フィッシングを防ぐことができます。 [office 365 atp safe links ポリシーを](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc)セットアップするか、 [office 365 atp safe links ポリシーを](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc)セットアップします。
    
- ユーザーのメールボックスを**訴訟ホールド**の対象にすることで、削除されたアイテムを含むすべてのメールボックスのコンテンツを保持できます。 手順については、 
- [Exchange Online アーカイブを使用してメールの保存期間を設定](security-features.md#set-up-email-retention-with-exchange-online-archiving)します。
    
- 保持期間の終了時に特定の時間だけ保持したり、コンテンツを完全に削除したりするために、カスタマイズされた**アイテム保持ポリシー**を設定します。 カスタマイズされたアイテム保持ポリシーは、セキュリティセンターとコンプライアンスセンターで有効にし、[**データガバナンス** \>の**保持**] に移動して、ウィザードの手順に従います。 詳細については、「[アイテム保持ポリシーの概要](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423)」を参照してください。
    
## <a name="next-steps"></a>次のステップ

ライセンスがあるユーザーは、次の手順でデバイスをセットアップします。<br/> 「[Microsoft 365 Business ユーザーの Windows デバイスをセットアップする](set-up-windows-devices.md)」と「[Microsoft 365 Business ユーザーのモバイル デバイスをセットアップする](set-up-mobile-devices.md)」を参照してください。 <br/>デバイスとアプリの保護ポリシーを設定する方法、およびユーザーのデバイスからデータを削除する方法に関する記事へのリンクについては、「[Microsoft 365 Business を管理する](manage.md)」を参照してください。 
  


