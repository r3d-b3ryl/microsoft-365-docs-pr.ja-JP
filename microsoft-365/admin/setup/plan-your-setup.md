---
title: Microsoft 365 for business のセットアップを計画する
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: eb926624-018b-4486-bf11-5fba6ee4d645
description: Microsoft 365 for business に移行する際の要件と考慮事項について説明します。
ms.openlocfilehash: b7d815da012e1c104561d5fccfb9e1704ac5c447
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529662"
---
# <a name="plan-your-setup-of-microsoft-365-for-business"></a>Microsoft 365 for business のセットアップを計画する

この記事は、Microsoft 365 for business プランに加入しているユーザーを対象としています。
  
組織を Microsoft 365 に移行する前に、満たす必要のある要件、必要な情報、必要な情報、および決定しなければならないことがあります。


  
## <a name="info-to-have-on-hand-before-you-run-the-setup-wizard"></a>セットアップウィザードを実行する前に手元にある情報

セットアップウィザードを実行して、ドメインを Microsoft 365 に移行する準備ができたら、次の情報を手元に置いておく必要があります。
  
- Microsoft 365 に追加するユーザーの一覧です。 既に Microsoft 365 に追加している場合でも、ドメイン情報を更新する場合は、ここで名前を入力する必要があります。

- ユーザーがサインインできるように、従業員に自分のユーザー ID とパスワードを通知する方法。 情報を使用してそれらを呼び出すことはできますか? または、個人のメールアドレスに送信しますか? ユーザーはメールにアクセスできないので、これを使用することはできません。

- 組織のドメイン名 (contoso.com**など) があり、Microsoft**電子メールの使用を計画している場合は、ドメインが登録されている場所とサインイン情報を知っている必要があります。

## <a name="what-happens-when-you-run-the-microsoft-365-setup-wizard"></a>Microsoft 365 セットアップウィザードを実行したときの処理

セットアップウィザードは、コンピューターへの Microsoft 365 アプリのインストール、ドメインの追加と検証、ユーザーの追加とライセンスの割り当て、ドメインの接続を行います。

> [!NOTE]
> Microsoft 365 で、ウィザードで追加するユーザーに[管理者ロールを割り当てる](../add-users/assign-admin-roles.md)必要がある場合は、後で [**ユーザー** ] ページでこれを行うことができます。 
  
セットアップウィザードを完了していない場合は、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)セットアップからいつでもセットアップタスクを完了でき  >  **Setup**ます。 このページから、別の電子メールサービスからメールと連絡先を移行したり、管理者アカウントのドメインを変更したり、ユーザーを追加または削除したり、パスワードをリセットしたり、その他のビジネス機能を実行したりすることができます。 セットアップウィザードと**セットアップ**ページの相違点の詳細については、「 [Microsoft 365 セットアップウィザードとセットアップページの相違点](o365-setup-wizard-and-setup-page.md)」を参照してください。

任意の時点で行き詰まった場合は、にお問い合わせください。 [ご参考になります。](../contact-support-for-business-products.md)
  
## <a name="when-not-to-use-the-setup-wizard-active-directory-synchronization-and-hybrid-environments"></a>セットアップ ウィザードを使用しない場合 Active Directory 同期とハイブリッド環境

オンプレミス環境からのデータまたはユーザーの移行、またはディレクトリ同期を含むハイブリッドシステムのセットアップを含むいくつかのシナリオがあります。 どちらかのカテゴリにいる場合は、次の記事の手順に従ってください。
  
- オンプレミスの Active Directory とのディレクトリ同期をセットアップするには、「 [microsoft 365 のディレクトリ同期をセットアップ](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)する」および「microsoft [365 Identity と Azure Active directory](https://docs.microsoft.com/office365/enterprise/about-office-365-identity)365 について」を参照してください。

- Exchange ハイブリッドを設定するには、ハイブリッド Exchange を設定する (DNS レコードの設定を含む) 異なるいくつかの方法のすべてについて説明した「[Exchange Server 展開アシスタント](https://aka.ms/exdeploy)」の詳しい手順を参照してください。

- SharePoint ハイブリッド、特にハイブリッド検索機能とサイト機能を設定するには、「[SharePoint のハイブリッド検索](https://docs.microsoft.com/SharePoint/hybrid/hybrid-search-in-sharepoint)」を参照してください。

## <a name="move-to-microsoft-365-all-at-once-or-in-stages"></a>Microsoft 365 全体または段階的に移行する

- **一度に組織を Microsoft 365 に移行しますか?** その場合は、ドメインを Microsoft 365 にすぐに移行することを計画します。 最初に、Microsoft 365 セットアップウィザードを実行します。ドメインのセットアップを求めるメッセージが表示されます。

- **Microsoft 365 に段階的に移行しますか?** Microsoft 365 に段階的に移行する場合は、Microsoft 365 セットアップウィザードの実行をスキップして、次の順序で Microsoft 365 機能を使用することを検討してください。

    1. Office アプリをダウンロードしてインストールできるように、[従業員を Microsoft 365 に追加](../add-users/add-users.md)します。

    2. コンピューターやデバイスで Word、Excel、および PowerPoint を使用するために、[Office アプリをダウンロードして、インストール](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)します。

    3. 会議に使用する[Microsoft Teams](#plan-for-teams)をセットアップします。

    4. [コンテンツを Microsoft 365 クラウドストレージ](set-up-file-storage-and-sharing.md)(OneDrive または SharePoint チームサイト) に移動します。

    5. 準備が整ったら、[管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で、左側のナビゲーションウィンドウで [**設定**] を選択し、[**セットアップ**] ページを使用し[てドメインと電子メールを移動](add-domain.md)します。

## <a name="check-that-your-devices-meet-system-requirements"></a>デバイスがシステム要件を満たしていることを確認する

組織内の各ユーザーは、最大5台の Pc と Mac にアプリの Office 2016 スイート (Word、Excel、PowerPoint など) をインストールできます。 法人向け [Office 2016 スイート](https://go.microsoft.com/fwlink/?LinkId=534827)をインストールするためのオペレーティング システムおよびコンピューターの要件を参照してください。
  
モバイルアプリは、iOS、Android、Windows デバイスにインストールできます。 モバイル デバイスとブラウザーのサポートについては、「[Office のシステム要件](https://go.microsoft.com/fwlink/?LinkId=534827)」を参照してください。
  
## <a name="plan-for-email"></a>メールの計画

既存の電子メールサービスから Microsoft 365 への移行を計画している場合は、通常、切り替えに2日かかることがあります。
  
### <a name="plan-for-email-downtime"></a>メールのダウンタイムの計画
  
メールに Microsoft 365 を使用する場合は、次のようにします。
  
- 会社の電子メールアドレス (*渡 \@ contoso.com*など) を別の電子メールサービスから microsoft 365 に移行するには、メールを新しい microsoft 365 メールボックスに配信するように指示する必要があります。 これを行うには、**セットアップ**ページで [**ユーザーのデータを移行**する] を選択します。ここでは、ドメインホストで行う必要のある更新プログラムについて手順を追って説明します。

- ドメイン ホストの更新後、変更は通常 1、2 時間で有効になります。 ただし、インターネット経由で変更が更新されるまでに最大72時間かかる場合があることに注意してください。

- メールのダウンタイムが発生する可能性があるため、受信するメールが少ない夜間または週末に Microsoft メールへの切り替えを計画することをお勧めします。

### <a name="plan-to-move-your-existing-email-contacts-and-calendar"></a>既存のメール、連絡先、予定表の移行の計画
  
電子メールアカウントに Microsoft 365 を使用する場合は、既存のメール、連絡先、予定表をお客様と一緒にご利用いただけます。 [**セットアップ**] ページでは、ほとんどのシナリオにおいて既存の電子メールと連絡先を移動するのに役立つ情報が表示されます。 また、1 つまたは複数のメールボックスを移行するためのステップ バイ ステップ ガイドも用意しています。
  
|**メールボックスの数**|**推奨事項**|
|:-----|:-----|
|少数  <br/> |**セットアップ**ページを使用してメールボックスを移行しない場合は、メールボックスの所有者が自分のメールと連絡先を移行できるようにすることができます。 [ビジネス向けの Microsoft 365 へのメールと連絡先の移行を](migrate-email-and-contacts-admin.md)参照してください。  <br/> |
|やや少数  <br/> |Gmail から移行している場合は、「 [Microsoft 365 への G Suite メールボックスの移行](https://docs.microsoft.com/Exchange/mailbox-migration/migrating-imap-mailboxes/migrate-g-suite-mailboxes)」を参照してください。  <br/> Exchange を含む別のメールプロバイダーから移行している場合は、「[複数のメールアカウントを Microsoft 365 に移行する方法](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)」を参照してください。  <br/> |

## <a name="plan-for-file-storage-and-migration"></a>ファイル ストレージと移行の計画

Microsoft 365 は、個人、小規模な組織、および企業向けにクラウドストレージを提供しています。 どこに保存するかについてのガイダンスについては、「 [Microsoft 365 でドキュメントを保存する場所](https://support.microsoft.com/office/c7c20284-bc94-47f4-9728-d28e9daf0790)」を参照してください。
  
- [OneDrive](https://support.microsoft.com/office/45114744-6D42-45CD-8975-F9617819BDEB)または[SharePoint チームサイト](https://support.microsoft.com/office/da549fb1-1fcb-4167-87d0-4693e93cb7a0#__toc384119242)に、**数百のファイルを移動することができ**ます。 一度に 100 個のファイルをアップロードできます。 ただし、ファイルの既定の最大サイズである 2 GB を超えるファイルはアップロードしないでください。
  
- **数千のファイル**を Microsoft 365 ストレージに移動する場合は、 [SharePoint Online の制限](https://go.microsoft.com/fwlink/p/?LinkID=856113)を確認してください。 移行ツールを使用するか、または移行を支援する[パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用を検討することをお勧めします。 大量のファイルを移行する方法については、「[SharePoint Online および OneDrive 移行ユーザー ガイド](https://go.microsoft.com/fwlink/?LinkId=723574)」を参照してください。
  
## <a name="plan-for-teams"></a>Teams を計画する

Microsoft Teams を使用して、サブスクリプションに参加している組織内の他のユーザーに電話をかけることができます。 たとえば、組織に10人のユーザーがいる場合、特別な設定なしで Teams を使用して、互いに通話と IM を行うことができます。 詳細については、「 [Microsoft Teams の使用を開始](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-quick-start)する」を参照してください。

大規模な組織の場合、または Skype for Business、社内、またはハイブリッド展開から開始する場合は、「 [Microsoft Teams をロールアウトする方法](https://docs.microsoft.com/MicrosoftTeams/how-to-roll-out-teams)」を参照してください。
  
## <a name="plan-for-integration-with-active-directory-or-other-software"></a>Active Directory やその他のソフトウェアとの統合の計画

- **オンプレミスの Active Directory と統合するかどうか。** Azure Active Directory Connect を使用して、オンプレミスの Active Directory を Microsoft 365 に統合することができます。 手順については、「 [Microsoft 365 のディレクトリ同期をセットアップする](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)」を参照してください。
  
- **Microsoft 365 を他の企業が作成したソフトウェアと統合するかどうか。** Microsoft 365 を組織内の他のソフトウェアと統合する必要がある場合は、展開を支援する[パートナーの採用](https://go.microsoft.com/fwlink/?linkid=391089)を検討することをお勧めします。
  
## <a name="do-you-want-someone-to-help-you-set-up-microsoft-365"></a>他のユーザーが Microsoft 365 をセットアップできるようにしますか。

- **従業員が 50 名未満の場合:**

  - **ヘルプを求めてお客様にご連絡**ください。 Microsoft 365 を購入すると、管理センターにアクセスできるようになります (取得するには、セットアッププログラムを実行する必要はありません)。 管理センターの下部で、[**ヘルプが必要ですか?** ] を選択します。 問題について説明し、お客様にご連絡します。 
  - ご**質問がある[場合は、Microsoft 365 For Business サポートに](../contact-support-for-business-products.md)お問い合わせ**ください。 We're here to help! 
  - **[Microsoft パートナー](https://go.microsoft.com/fwlink/?linkid=391089)の採用をご検討ください** 。 時間が足りない場合や、高度な要件 (Microsoft 365 クラウドストレージへのファイルの移動や他のソフトウェアとの統合など) がある場合は、経験豊富なパートナーが大きなヘルプになることがあります。 

- **50 名以上の従業員がいる場合** 、 [FastTrack オンボーディング センター](https://go.microsoft.com/fwlink/?LinkId=517115)が展開をサポートします。 
