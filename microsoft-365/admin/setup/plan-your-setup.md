---
title: Microsoft 365 for business のセットアップを計画する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: ビジネス向け Microsoft 365 への移行に関する要件と考慮事項について説明します。
ms.openlocfilehash: 7ec1fae211ec42afd510ee431a3ea7e17e2fd16b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914068"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Microsoft 365 for business のセットアップを計画する

この記事は、Microsoft 365 for business プランを購読しているユーザー向けです。
  
組織を Microsoft 365 に移行する前に、満たす必要がある要件、必要な情報、および決定を行う必要があります。


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>セットアップ ウィザードを実行する前に必要な情報

セットアップ ウィザードを実行し、ドメインを Microsoft 365 に移動する準備ができたら、必要な情報を次に示します。
  
- Microsoft 365 に追加するユーザーの一覧。 Microsoft 365 に追加済みの場合でも、ドメイン情報を更新する場合は、ここに名前を入力する必要があります。

- 従業員がサインインできるよう、従業員にユーザー ID とパスワードを通知する方法。 情報を使用してそれらを呼び出すつもりですか? または、個人の電子メール アドレスに送信しますか? メールにアクセスできないので、使用することはできません。

- 組織のドメイン名 (contoso.com **など)** を持ち、Microsoft メールの使用を計画している場合は、ドメインが登録されている場所を知り、サインイン情報を持っている必要があります。

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Microsoft 365 セットアップ ウィザードを実行するとどうなるか

セットアップ ウィザードでは、Microsoft 365 アプリをコンピューターにインストールし、ドメインの追加と検証、ユーザーの追加とライセンスの割り当て、ドメインの接続について説明します。

> [!NOTE]
> Microsoft [365](../add-users/assign-admin-roles.md) for business の管理者ロールをウィザードで追加したユーザーに割り当てる必要がある場合は、後で [ユーザー] ページで **行** います。 
  
セットアップ ウィザードを完了しない場合は、管理センターのセットアップからいつでもセットアップ [タスクを完了](https://go.microsoft.com/fwlink/p/?linkid=2024339)  >  **できます**。 ここから、別のメール サービスからメールと連絡先を移行したり、管理者アカウントのドメインを変更したり、請求情報を管理したり、ユーザーを追加または削除したり、パスワードをリセットしたり、その他のビジネス機能を実行できます。 セットアップ ウィザードとセットアップ ページの違いの詳細については[、「Microsoft 365](o365-setup-wizard-and-setup-page.md)セットアップ ウィザードとセットアップ ページの違い」を参照してください。 

任意の時点で立ち往生した場合は、お電話ください。 [お手伝いします!](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>セットアップ ウィザードを使用しない場合 Active Directory 同期とハイブリッド環境

データまたはユーザーをオンプレミス環境から移行するか、ディレクトリ同期を含むハイブリッド システムをセットアップするシナリオが複数存在します。 いずれかのカテゴリに入っている場合は、次の記事の手順に従います。
  
- オンプレミスの Active Directory とのディレクトリ同期を設定するには、「Microsoft 365 のディレクトリ同期をセットアップする」を参照し [、Microsoft 365](../../enterprise/set-up-directory-synchronization.md)の異なる ID モデルを理解するには [、「Microsoft 365 IDENTITY](../../enterprise/about-microsoft-365-identity.md)と Azure Active Directory について」を参照してください。

- Exchange ハイブリッドを設定するには、ハイブリッド Exchange を設定する (DNS レコードの設定を含む) 異なるいくつかの方法のすべてについて説明した「[Exchange Server 展開アシスタント](/exchange/exchange-deployment-assistant)」の詳しい手順を参照してください。

- SharePoint ハイブリッド、特にハイブリッド検索機能とサイト機能を設定するには、「[SharePoint のハイブリッド検索](/SharePoint/hybrid/hybrid-search-in-sharepoint)」を参照してください。

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Microsoft 365 に一度または複数の段階で移動する

- **組織を Microsoft 365 に一度に移動しますか?** その場合は、ドメインを Microsoft 365 に簡単に移動する予定です。 まず、Microsoft 365 セットアップ ウィザードを実行します。ドメインのセットアップを求めるメッセージが表示されます。

- **Microsoft 365 に徐々に移行しますか?** ステージで Microsoft 365 に移行する場合は、Microsoft 365 セットアップ ウィザードの実行をスキップし、次の順序で Microsoft 365 機能の採用を検討してください。

    1. [Microsoft 365 に従業員を追加して](../add-users/add-users.md) 、ユーザーがアプリをダウンロードしてインストールOfficeします。

    2. コンピューターやデバイスで Word、Excel、および PowerPoint を使用するために、[Office アプリをダウンロードして、インストール](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)します。

    3. [会議に使用する Microsoft Teams](#plan-for-teams) をセットアップします。

    4. [コンテンツを Microsoft 365 クラウド](set-up-file-storage-and-sharing.md) ストレージ (OneDrive または SharePoint チーム サイト) に移動します。

    5. 準備ができたら、管理センターで左側の[](https://go.microsoft.com/fwlink/p/?linkid=2024339)ナビゲーション ウィンドウで[セットアップ] を選択し、[セットアップ] ページを使用してドメインとメール[を移動します](add-domain.md)。

## <a name="check-that-your-devices-meet-system-requirements"></a>デバイスがシステム要件を満たしていることを確認する

組織内の各ユーザーは、Office 2016 スイートのアプリ (Word、Excel、PowerPoint など) を最大 5 台の PC と Mac にインストールできます。 法人向け [Office 2016 スイート](https://go.microsoft.com/fwlink/?LinkId=534827)をインストールするためのオペレーティング システムおよびコンピューターの要件を参照してください。
  
モバイル アプリは、iOS、Android、および Windows デバイスにインストールできます。 モバイル デバイスとブラウザーのサポートについては、「[Office のシステム要件](https://go.microsoft.com/fwlink/?LinkId=534827)」を参照してください。
  
## <a name="plan-for-email"></a>メールの計画

既存のメール サービスから Microsoft 365 への移行を計画している場合は、通常、切り替えに 2 日かかる。
  
### <a name="plan-for-email-downtime"></a>メールのダウンタイムの計画
  
メールに Microsoft 365 を使用する場合:
  
- ビジネス用メール アドレス *(rob \@ contoso.com* など) を別のメール サービスから Microsoft 365 に移動するには、新しい Microsoft 365 メールボックスにメールを配信する必要があります。 これを行うには、[セットアップ]ページで [ユーザーのデータを移行する] を選択します。ここでは、ドメイン ホストで行う必要がある更新プログラムについて、手順に従って説明します。

- ドメイン ホストの更新後、変更は通常 1、2 時間で有効になります。 ただし、変更がインターネット上で更新されるのに最大で 72 時間かかる場合があります。

- 電子メールのダウンタイムが発生する可能性がある場合は、メールの受信が少ない夜間または週末に Microsoft メールに切り替える予定をお勧めします。

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>既存のメール、連絡先、予定表の移行の計画
  
メール アカウントに Microsoft 365 を使用する場合は、既存のメール、連絡先、予定表を持参できます。 [ **セットアップ]** ページは、ほとんどのシナリオで既存のメールと連絡先を移動するのに役立ちます。 また、1 つまたは複数のメールボックスを移行するためのステップ バイ ステップ ガイドも用意しています。
  
|**メールボックスの数**|**推奨事項**|
|:-----|:-----|
|少数  <br/> |[セットアップ] ページを使用してメールボックスを移行しない場合は、メールボックスの所有者が自分の電子メールと連絡先を移行できます。 「 [メールと連絡先を Microsoft 365 for business に移行する」を参照してください](migrate-email-and-contacts-admin.md)。  <br/> |
|やや少数  <br/> |Gmail から移行する場合は、「G Suite メールボックスを [Microsoft 365 に移行する」を参照してください](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)。  <br/> Exchange を含む別の電子メール プロバイダーから移行する場合は、「複数の電子メール アカウントを [Microsoft 365](/Exchange/mailbox-migration/mailbox-migration)に移行する方法」を参照してください。  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>ファイル ストレージと移行の計画

Microsoft 365 は、個人、小規模組織、および企業向けクラウド ストレージを提供します。 保存場所のガイダンスについては [、「Microsoft 365](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)でドキュメントを保存できる場所」を参照してください。
  
- **何百ものファイルを** [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) または [SharePoint チーム サイトに移動できます](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)。 一度に 100 個のファイルをアップロードできます。 ただし、ファイルの既定の最大サイズである 2 GB を超えるファイルはアップロードしないでください。
  
- **数千のファイルを** Microsoft 365 ストレージに移動する場合は [、SharePoint Online の制限を確認してください](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)。 移行ツールを使用するか、または移行を支援する[パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討することをお勧めします。 大量のファイルを移行する方法については、「[SharePoint Online および OneDrive 移行ユーザー ガイド](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)」を参照してください。
  
## <a name="plan-for-teams"></a>Teams の計画

Microsoft Teams を使用して、サブスクリプションに参加している組織内の他のユーザーに通話を行います。 たとえば、組織に 10 人のユーザーがある場合は、特別なセットアップを行わずに Teams を使用して互いに通話と IM を実行できます。 詳細については、「Microsoft Teams の使用 [を開始する」を参照してください](/MicrosoftTeams/get-started-with-teams-quick-start)。

大規模な組織の場合、または Skype for Business、オンプレミス、またはハイブリッド展開から始める場合は [、「How to roll out Microsoft Teams](/MicrosoftTeams/how-to-roll-out-teams)」を参照してください。
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Active Directory やその他のソフトウェアとの統合の計画

- **オンプレミスの Active Directory と統合しますか?** Azure Active Directory Connect を使用して、オンプレミスの Active Directory を Microsoft 365 と統合できます。 手順については [、「Microsoft 365 のディレクトリ同期をセットアップする」を参照してください](../../enterprise/set-up-directory-synchronization.md)。
  
- **Microsoft 365 と他の会社製のソフトウェアを統合しますか?** Microsoft 365 を組織内の他のソフトウェアと統合する必要がある場合は、[](https://go.microsoft.com/fwlink/?linkid=391089)展開に役立つパートナーを採用することを検討することをお勧めします。
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Microsoft 365 のセットアップを支援するユーザーが必要ですか?

- **従業員が 50 名未満の場合:**

  - **ヘルプを求め、お電話します**。 Microsoft 365 を購入した後、管理センターにアクセスできます (セットアップを実行してアクセスする必要があります)。 管理センターの下部で、[ヘルプが必要] **を選択します。** 問題を説明し、お客様に電話します。 
  - **ご質問 [がある場合は、Microsoft 365 for Business サポート](../contact-support-for-business-products.md) にお問い合わせください**。 We're here to help! 
  - **[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用をご検討ください** 。 時間が短い場合や、高度な要件 (何千ものファイルを Microsoft 365 クラウド ストレージに移動する、他のソフトウェアと統合するなど) がある場合は、経験豊富なパートナーが大きな助けになります。 

- **50 名以上の従業員がいる場合** 、 [FastTrack オンボーディング センター](https://go.microsoft.com/fwlink/?LinkId=517115)が展開をサポートします。