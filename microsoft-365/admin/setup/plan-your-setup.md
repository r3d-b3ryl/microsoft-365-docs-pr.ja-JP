---
title: Microsoft 365 for business のセットアップを計画
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_O365_Setup
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: ビジネス向けサービスへの移行に関する要件と考慮事項Microsoft 365説明します。
ms.openlocfilehash: f02cd28c403cbe5b27b427fae94975ec4b608591
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2021
ms.locfileid: "61373034"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Microsoft 365 for business のセットアップを計画

この記事は、ビジネス プランに関するMicrosoft 365ユーザー向けです。
  
組織を組織を Microsoft 365する前に、満たす必要がある要件、必要な情報、および決定を行う必要があります。

## <a name="overview-of-microsoft-365-business-premium-setup"></a>セットアップのMicrosoft 365 Business Premium概要

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg?autoplay=false]

ビジネスをクラウドに移行する決定をおめでとうございます。Microsoft 365! ビジネスに 1 人か 20 人か、少し計画を立て、自分の仕事をMicrosoft 365 Business Premium。

## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>セットアップ ウィザードを実行する前に必要な情報

セットアップ ウィザードを実行し、ドメインを Microsoft 365 に移動する準備ができたら、次の情報が必要です。
  
- ユーザーに追加するユーザーの一Microsoft 365。 ドメイン情報を更新する場合は、Microsoft 365に追加した場合でも、ここに名前を入力する必要があります。

- 従業員がサインインできるよう、従業員にユーザー ID とパスワードを通知する方法。 情報を使用してそれらを呼び出すつもりですか? または、個人の電子メール アドレスに送信しますか? メールにアクセスできないので、使用することはできません。

- 組織のドメイン名 (contoso.com **など)** を持ち、Microsoft メールの使用を計画している場合は、ドメインが登録されている場所を知り、サインイン情報を持っている必要があります。

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>セットアップ ウィザードを実行するとMicrosoft 365する

セットアップ ウィザードでは、Microsoft 365 アプリをコンピューターにインストールする方法、ドメインの追加と確認、ユーザーの追加とライセンスの割り当て、ドメインの接続について説明します。

> [!NOTE]
> ウィザード [で追加した](../add-users/assign-admin-roles.md)ユーザーにビジネスMicrosoft 365管理者ロールを割り当てる必要がある場合は、後で [ユーザー] ページで **行** います。 
  
セットアップ ウィザードを完了しない場合は、管理センターのセットアップからいつでもセットアップ [タスクを完了](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **できます**。 ここから、別のメール サービスからメールと連絡先を移行したり、管理者アカウントのドメインを変更したり、請求情報を管理したり、ユーザーを追加または削除したり、パスワードをリセットしたり、その他のビジネス機能を実行できます。 セットアップ ウィザードと [セットアップ] ページの違いの詳細については、「セットアップ ウィザードとセットアップ ページMicrosoft 365違い」を[参照してください](o365-setup-wizard-and-setup-page.md)。

任意の時点で立ち往生した場合は、お電話ください。 [ここにお手伝いします。](../../business-video/get-help-support.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>セットアップ ウィザードを使用しない場合 Active Directory 同期とハイブリッド環境

データまたはユーザーをオンプレミス環境から移行するか、ディレクトリ同期を含むハイブリッド システムをセットアップするシナリオが複数存在します。 いずれかのカテゴリに入っている場合は、次の記事の手順に従います。
  
- オンプレミスの Active Directory とのディレクトリ同期を設定するには、「Microsoft 365 のディレクトリ同期をセットアップする」を参照し[、Microsoft 365](../../enterprise/set-up-directory-synchronization.md)の異なる ID モデルを理解するには、「Microsoft 365 ID と Azure Active Directory について」を[参照](../../enterprise/about-microsoft-365-identity.md)してください。

- Exchange ハイブリッドを設定するには、ハイブリッド Exchange を設定する (DNS レコードの設定を含む) 異なるいくつかの方法のすべてについて説明した「[Exchange Server 展開アシスタント](/exchange/exchange-deployment-assistant)」の詳しい手順を参照してください。

- SharePoint ハイブリッド、特にハイブリッド検索機能とサイト機能を設定するには、「[SharePoint のハイブリッド検索](/SharePoint/hybrid/hybrid-search-in-sharepoint)」を参照してください。

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>一度Microsoft 365またはステージに移動する

- **組織をすべてのユーザーに一度にMicrosoft 365しますか?** その場合は、ドメインをドメインに移動し、Microsoft 365に移動します。 まず、セットアップ ウィザードMicrosoft 365実行します。ドメインのセットアップを求めるメッセージが表示されます。

- **徐々に新しいMicrosoft 365しますか?** ステージ内の Microsoft 365 に移動する場合は、Microsoft 365 セットアップ ウィザードの実行をスキップし、次の順序でMicrosoft 365機能の採用を検討してください。

    1. [従業員がアプリをダウンロードMicrosoft 365](../add-users/add-users.md)インストールできるよう、従業員をOfficeします。

    2. コンピューターやデバイスで Word、Excel、および PowerPoint を使用するために、[Office アプリをダウンロードして、インストール](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)します。

    3. [会議にMicrosoft Teams](#plan-for-teams)を設定します。

    4. [コンテンツをクラウド ストレージMicrosoft 365 (チーム](set-up-file-storage-and-sharing.md)サイトOneDriveまたはSharePoint移動します。

    5. 準備ができたら、管理センターで左側の[](https://go.microsoft.com/fwlink/p/?linkid=2024339)ナビゲーション ウィンドウで[セットアップ] を選択し、[セットアップ] ページを使用してドメインとメール[を移動します](add-domain.md)。

## <a name="check-that-your-devices-meet-system-requirements"></a>デバイスがシステム要件を満たしていることを確認する

組織内の各ユーザーは、Office 2016 スイートのアプリ (Word、Excel、PowerPoint など) を最大 5 台の PC と Mac にインストールできます。 法人向け [Office 2016 スイート](https://go.microsoft.com/fwlink/?LinkId=534827)をインストールするためのオペレーティング システムおよびコンピューターの要件を参照してください。
  
モバイル アプリは、iOS、Android、およびモバイル デバイスWindowsできます。 モバイル デバイスとブラウザーのサポートについては、「[Office のシステム要件](https://go.microsoft.com/fwlink/?LinkId=534827)」を参照してください。
  
## <a name="plan-for-email"></a>メールの計画

既存のメール サービスからメール サービスへの移行を計画している場合Microsoft 365、通常、切り替えに 2 日かかる。
  
### <a name="plan-for-email-downtime"></a>メールのダウンタイムの計画
  
メールにメールをMicrosoft 365する場合は、次のMicrosoft 365を使用します。
  
- ビジネス用メール アドレス *(rob \@ contoso.com* など) を別のメール サービスから Microsoft 365 に移動するには、新しい電子メール メールボックスにメールを配信Microsoft 365する必要があります。 これを行うには、[セットアップ]ページで [ユーザーのデータを移行する] を選択します。ここでは、ドメイン ホストで行う必要がある更新プログラムについて、手順に従って説明します。

- ドメイン ホストの更新後、変更は通常 1、2 時間で有効になります。 ただし、変更がインターネット上で更新されるのに最大で 72 時間かかる場合があります。

- 電子メールのダウンタイムが発生する可能性がある場合は、メールの受信が少ない夜間または週末に Microsoft メールに切り替える予定をお勧めします。

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>既存のメール、連絡先、予定表の移行の計画
  
電子メール アカウントに Microsoft 365を使用する場合は、既存のメール、連絡先、予定表を持ち込む必要があります。 [ **セットアップ]** ページは、ほとんどのシナリオで既存のメールと連絡先を移動するのに役立ちます。 また、1 つまたは複数のメールボックスを移行するためのステップ バイ ステップ ガイドも用意しています。
  
|**メールボックスの数**|**推奨事項**|
|:-----|:-----|
|少数  <br/> |[セットアップ] ページを使用してメールボックスを移行しない場合は、メールボックスの所有者が自分の電子メールと連絡先を移行できます。 「[メールと連絡先をビジネス向けMicrosoft 365移行する」を参照してください](migrate-email-and-contacts-admin.md)。  <br/> |
|やや少数  <br/> |Gmail から移行する場合は、「G Suite メールボックスを移行する」を参照[Microsoft 365。](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)  <br/> 別の電子メール プロバイダー (Exchange を含む) から移行する場合は、「複数の電子メール アカウントを別のメール プロバイダーに移行する方法」[をMicrosoft 365。](/Exchange/mailbox-migration/mailbox-migration)  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>ファイル ストレージと移行の計画

Microsoft 365、小規模組織、および企業向けクラウド ストレージを提供します。 保存場所のガイダンスについては、「ドキュメントを保存できる場所[」](https://support.microsoft.com/office/d18d21a0-1f9f-4f6c-ac45-d52afa0a4a2e)を参照Microsoft 365。
  
- **何百ものファイルを、OneDrive**[チーム](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB)サイト [SharePoint移動できます](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)。 一度に 100 個のファイルをアップロードできます。 ただし、ファイルの既定の最大サイズである 2 GB を超えるファイルはアップロードしないでください。
  
- **数千のファイルをストレージに** 移動するMicrosoft 365、オンライン制限のSharePoint [確認してください](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)。 移行ツールを使用するか、または移行を支援する[パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討することをお勧めします。 大量のファイルを移行する方法については、「[SharePoint Online および OneDrive 移行ユーザー ガイド](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)」を参照してください。
  
## <a name="plan-for-teams"></a>計画を立Teams

サブスクリプションを使用Microsoft Teams組織内の他のユーザーに通話を行う場合に使用できます。 たとえば、組織に 10 人のユーザーが含む場合は、特別なセットアップを行わずに、Teamsを使用して互いに呼び出し、IM を実行できます。 詳細については、「Get [started with Microsoft Teams」 を参照してください](/MicrosoftTeams/get-started-with-teams-quick-start)。

大規模な組織の場合、または Skype for Business、オンプレミス、またはハイブリッド展開から開始する場合は、「組織を展開する方法」を[Microsoft Teams。](/MicrosoftTeams/how-to-roll-out-teams)
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Active Directory やその他のソフトウェアとの統合の計画

- **オンプレミスの Active Directory と統合しますか?** オンプレミスの Active Directory を、オンプレミスの Active Directory とMicrosoft 365を使用Azure Active Directory Connect。 手順については、「ディレクトリ同期[のセットアップ」を参照Microsoft 365。](../../enterprise/set-up-directory-synchronization.md)
  
- **他の企業がMicrosoft 365と統合しますか?** 組織の他のソフトウェアMicrosoft 365統合する必要がある場合は、展開に役立つパートナーを[](https://go.microsoft.com/fwlink/?linkid=391089)採用することを検討することをお勧めします。
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>ユーザーがユーザーの設定を支援Microsoft 365?

- **従業員が 50 名未満の場合:**

  - **ヘルプを求め、お電話します**。 アプリを購入Microsoft 365管理センターにアクセスできます (セットアップを実行して管理センターにアクセスする必要があります)。 管理センターの下部で、[ヘルプが必要] **を選択します。** 問題を説明し、お客様に電話します。 
  - **ご質問 [Microsoft 365、ビジネス サポートに問い](../../business-video/get-help-support.md)合わせください**。 We're here to help! 
  - **[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用をご検討ください** 。 時間が短い場合や、高度な要件 (何千ものファイルを Microsoft 365 クラウド ストレージに移動したり、他のソフトウェアと統合したり) がある場合は、経験豊富なパートナーが大きな助けになります。 

- **50 名以上の従業員がいる場合** 、 [FastTrack オンボーディング センター](https://go.microsoft.com/fwlink/?LinkId=517115)が展開をサポートします。