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
- adminvideo
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Microsoft 365 for Business への移行に関する要件と考慮事項について説明します。
ms.openlocfilehash: 356d4cc1f696c871badcdceeb392c74b510cb49c
ms.sourcegitcommit: e9692a40dfe1f8c2047699ae3301c114a01b0d3a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/01/2022
ms.locfileid: "66601160"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Microsoft 365 for business のセットアップを計画

YouTube の [Microsoft 365 小規模ビジネス ヘルプ](https://go.microsoft.com/fwlink/?linkid=2197659) を確認してください。

この記事は、ビジネス プラン用の Microsoft 365 をサブスクライブしているユーザーを対象にしています。
  
組織を Microsoft 365 に移行する前に、満たす必要がある要件、手元に必要な情報、決定する必要があります。

## <a name="overview-of-microsoft-365-for-business-setup"></a>ビジネス向け Microsoft 365 のセットアップの概要

[YouTube チャンネル](https://go.microsoft.com/fwlink/?linkid=2197910)で、このビデオや他の動画を確認してください。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Vjso?autoplay=false]

Microsoft 365 を使用してビジネスをクラウドに移行するという決定におめでとうございます。 ビジネスに 1 人でも 20 人でも、少し計画を立てると、ビジネス向けの Microsoft 365 を最大限に活用するのに役立ちます。

## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>セットアップ ウィザードを実行する前に手元にある情報

セットアップ ウィザードを実行し、ドメインを Microsoft 365 に移動する準備ができたら、手元に用意しておく必要がある情報を次に示します。
  
- Microsoft 365 に追加するユーザーの一覧。 Microsoft 365 に既に追加している場合でも、ドメイン情報を更新する場合は、ここに名前を入力する必要があります。

- サインインできるように、従業員にユーザー ID とパスワードを通知する方法。 情報を使用して呼び出す予定はありますか? または、個人の電子メール アドレスに送信しますか? 電子メールにアクセスできないため、メールを使用することはできません。

- 組織のドメイン名 (contoso.com **など) があり** 、Microsoft メールの使用を計画している場合は、ドメインが登録されている場所を把握し、サインイン情報を持っている必要があります。

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Microsoft 365 セットアップ ウィザードを実行するとどうなりますか

セットアップ ウィザードでは、コンピューターへの Microsoft 365 アプリのインストール、ドメインの追加と確認、ユーザーの追加とライセンスの割り当て、ドメインの接続について説明します。

> [!NOTE]
> ウィザードで追加したユーザー [にビジネス向け Microsoft 365 で管理者ロールを割り当てる](../add-users/assign-admin-roles.md) 必要がある場合は、後で [ **ユーザー]** ページでこれを行うことができます。 
  
セットアップ ウィザードを完了しない場合は、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339) > のセットアップからいつでもセットアップ タスク **を** 完了できます。 ここから、メールと連絡先を別のメール サービスから移行したり、管理者アカウントのドメインを変更したり、課金情報を管理したり、ユーザーを追加または削除したり、パスワードをリセットしたり、その他のビジネス機能を実行したりできます。 セットアップ ウィザードと **セットアップ ページの** 違いの詳細については、「 [Microsoft 365 セットアップ ウィザードとセットアップ ページの違い」を](o365-setup-wizard-and-setup-page.md)参照してください。

任意の時点でスタックした場合は、お問い合わせください。 [こちらにお問い合わせください。](../../business-video/get-help-support.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>セットアップ ウィザードを使用しない場合 Active Directory 同期とハイブリッド環境

オンプレミス環境からのデータまたはユーザーの移行や、ディレクトリ同期を含むハイブリッド システムの設定など、いくつかのシナリオがあります。 どちらのカテゴリにも該当する場合は、次の記事の手順に従います。
  
- オンプレミスの Active Directoryとのディレクトリ同期を設定するには、「[Microsoft 365 のディレクトリ同期を設定](../../enterprise/set-up-directory-synchronization.md)する」を参照し、Microsoft 365 のさまざまな ID モデルについて理解するには、「[Microsoft 365 の ID インフラストラクチャをデプロイする](../../enterprise/deploy-identity-solution-overview.md)」を参照してください。

- Exchange ハイブリッドを設定するには、ハイブリッド交換を設定するさまざまな方法 (DNS レコードの設定を含む) をガイドする手順の完全なセットをExchange Server[展開アシスタント](/exchange/exchange-deployment-assistant)を参照してください。

- SharePoint ハイブリッド、特にハイブリッド検索機能とサイト機能を設定するには、「[SharePoint のハイブリッド検索](/SharePoint/hybrid/hybrid-search-in-sharepoint)」を参照してください。

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Microsoft 365 に一度または段階的に移行する

- **組織を一度に Microsoft 365 に移行しますか?** その場合は、すぐにドメインを Microsoft 365 に移動する予定です。 まず、Microsoft 365 セットアップ ウィザードを実行します。ドメインの設定を求めるメッセージが表示されます。

- **Microsoft 365 に段階的に移行しますか?** 段階的に Microsoft 365 に移行する場合は、Microsoft 365 セットアップ ウィザードの実行をスキップし、次の順序で Microsoft 365 の機能を採用することを検討してください。

    1. Office アプリをダウンロードしてインストールできるように、[従業員を Microsoft 365 に追加](../add-users/add-users.md)します。

    2. コンピューターやデバイスで Word、Excel、および PowerPoint を使用するために、[Office アプリをダウンロードして、インストール](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)します。

    3. 会議に使用するように [Microsoft Teams を設定](#plan-for-teams)します。

    4. [コンテンツを Microsoft 365 クラウド ストレージ](set-up-file-storage-and-sharing.md) (OneDrive または SharePoint チーム サイト) に移動します。

    5. 準備ができたら、 [管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で左側のナビゲーション ウィンドウで **[セットアップ** ] を選択し、[ **セットアップ]** ページを使用して [ドメインとメールを移動します](add-domain.md)。

## <a name="check-that-your-devices-meet-system-requirements"></a>デバイスがシステム要件を満たしていることを確認する

組織内の各ユーザーは、Office 2016 スイートのアプリ (Word、Excel、PowerPoint など) を最大 5 台の PC と Mac にインストールできます。 法人向け [Office 2016 スイート](https://go.microsoft.com/fwlink/?LinkId=534827)をインストールするためのオペレーティング システムおよびコンピューターの要件を参照してください。
  
モバイル アプリは、iOS、Android、Windows デバイスにインストールできます。 モバイル デバイスとブラウザーのサポートについては、「[Office のシステム要件](https://go.microsoft.com/fwlink/?LinkId=534827)」を参照してください。
  
## <a name="plan-for-email"></a>メールの計画

既存のメール サービスから Microsoft 365 への移行を計画している場合は、通常、切り替えに 2 日かかります。
  
### <a name="plan-for-email-downtime"></a>メールのダウンタイムの計画
  
メールに Microsoft 365 を使用する場合:
  
- 別のメール サービスから Microsoft 365 にビジネスメール アドレス ( *強盗\@contoso.com* など) を移動するには、新しい Microsoft 365 メールボックスに配信されるようにメールを送信する必要があります。 これを行うには、[**セットアップ]** ページで **[ユーザーのデータの移行**] を選択します。ここでは、ドメイン ホストで行う必要がある更新プログラムを段階的に説明します。

- ドメイン ホストの更新後、変更は通常 1、2 時間で有効になります。 ただし、変更がインターネット経由で更新されるまでに最大で 72 時間かかる場合があることに注意してください。

- メールのダウンタイムが発生する可能性があるため、メールの受信数が少ない夜間または週末に Microsoft メールに切り替える予定をお勧めします。

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>既存のメール、連絡先、予定表の移行の計画
  
メール アカウントに Microsoft 365 を使用する場合は、既存のメール、連絡先、予定表を持ち込むことができます。 **[セットアップ]** ページは、ほとんどのシナリオで既存のメールと連絡先を移動するのに役立ちます。 また、1 つまたは複数のメールボックスを移行するためのステップ バイ ステップ ガイドも用意しています。
  
|**メールボックスの数**|**推奨事項**|
|:-----|:-----|
|少数  <br/> |**[セットアップ]** ページを使用してメールボックスを移行したくない場合は、メールボックスの所有者が自分のメールと連絡先を移行できるようにします。 [ビジネス向けの Microsoft 365 へのメールと連絡先の移行に関するページを](migrate-email-and-contacts-admin.md)参照してください。  <br/> |
|やや少数  <br/> |Gmail から移行する場合は、「 [G Suite メールボックスを Microsoft 365 に移行する」を](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)参照してください。  <br/> Exchange を含む別のメール プロバイダーから移行する場合は、「 [複数のメール アカウントを Microsoft 365 に移行する方法](/Exchange/mailbox-migration/mailbox-migration)」を参照してください。  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>ファイル ストレージと移行の計画

Microsoft 365 は、個人、小規模組織、企業向けにクラウド ストレージを提供します。 保存場所の詳細については、「 [Microsoft 365 でドキュメントを保存できる場所」を](https://support.microsoft.com/office/d18d21a0-1f9f-4f6c-ac45-d52afa0a4a2e)参照してください。
  
- **何百ものファイル** を [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB) または [SharePoint チーム サイト](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)に移動できます。 一度に 100 個のファイルをアップロードできます。 ただし、ファイルの既定の最大サイズである 2 GB を超えるファイルはアップロードしないでください。
  
- Microsoft 365 ストレージ **に数千個のファイルを移動する場合** は、[SharePoint Online の制限](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)を確認してください。 移行ツールを使用するか、または移行を支援する[パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討することをお勧めします。 大量のファイルを移行する方法については、「[SharePoint Online および OneDrive 移行ユーザー ガイド](/sharepointmigration/upload-on-premises-content-to-sharepoint-online-using-powershell-cmdlets)」を参照してください。
  
## <a name="plan-for-teams"></a>Teams の計画

Microsoft Teams を使用して、サブスクリプションに参加している組織内の他のユーザーに通話を発信できます。 たとえば、組織に 10 人のユーザーがいる場合は、Teams を使用して通話と IM を行うことができます。特別な設定は必要ありません。 詳細については、「 [Microsoft Teams の使用を開始](/MicrosoftTeams/get-started-with-teams-quick-start)する」を参照してください。

大規模な組織の場合、またはSkype for Business、オンプレミス、またはハイブリッドの展開から始める場合は、「[Microsoft Teams をロールアウトする方法」を](/MicrosoftTeams/how-to-roll-out-teams)参照してください。
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Active Directory やその他のソフトウェアとの統合の計画

- **オンプレミスの Active Directoryと統合しますか?** Azure Active Directory Connect を使用して、オンプレミスの Active Directoryを Microsoft 365 と統合できます。 手順については、「 [Microsoft 365 のディレクトリ同期を設定する」を](../../enterprise/set-up-directory-synchronization.md)参照してください。
  
- **Microsoft 365 を他の会社が作成したソフトウェアと統合しますか?** Microsoft 365 を組織内の他のソフトウェアと統合する必要がある場合は、展開に役立つ [パートナーを採用](https://go.microsoft.com/fwlink/?linkid=391089) することを検討することをお勧めします。
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>Microsoft 365 のセットアップを他のユーザーにサポートしてもらう必要がありますか?

- **従業員が 50 名未満の場合:**

  - **お問い合わせください。お電話でお問い合わせください**。 Microsoft 365 を購入した後、管理センターにアクセスできます (セットアップを実行してアクセスする必要はありません)。 管理センターの下部にある [ **ヘルプが必要ですか?** 問題を説明すると、お電話でお問い合わされます。 
  - **質問がある [場合は、Microsoft 365 for Business サポート](../../business-video/get-help-support.md) にお問い合わせください**。 We're here to help! 
  - **[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用をご検討ください** 。 時間が足りない場合や、高度な要件 (数千のファイルを Microsoft 365 クラウド ストレージに移動したり、他のソフトウェアと統合したりする場合など) がある場合は、経験豊富なパートナーが大きな助けになる可能性があります。 

- **50 名以上の従業員がいる場合** 、 [FastTrack オンボーディング センター](https://go.microsoft.com/fwlink/?LinkId=517115)が展開をサポートします。

## <a name="see-also"></a>関連項目

[ビジネス プランの Microsoft 365 をセキュリティで保護するためのベスト プラクティス](../security-and-compliance/secure-your-business-data.md)
