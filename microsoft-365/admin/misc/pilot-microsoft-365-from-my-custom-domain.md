---
title: カスタムドメインから Microsoft 365 をパイロットする
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom:
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
description: 2つのテストアカウントのみを使用して、カスタムドメインから Microsoft 365 メールボックスに電子メール機能をパイロットする方法について説明します。
ms.openlocfilehash: 6980480893e3e544a912edbe7d7da0993e781df2
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59178791"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>カスタムドメインから Microsoft 365 をパイロットする

次の要件と制限を使用して Microsoft 365 をパイロットできます。

- 現在の電子メール プロバイダーで、電子メール転送のサービスが提供されている必要があります。

- Microsoft 365 にこれらのレコードを管理させるのではなく、DNS ホスティングプロバイダーでMicrosoft 365 DNS レコードを管理する必要があります。

    詳細については、「[DNSレコードを追加してドメインに接続する](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)」をご覧ください。

- 他の電子メールサーバーのユーザーの空き時間情報は利用できません。

- 管理者が 1 つの場所からすべてのユーザーアカウントを管理することはできません。

- ユーザーが Microsoft 365 スパムフィルターを使用できない場合があります。

- これは、ユーザー数が非常に少ない場合にお勧めです。パイロット用にメールを使用する場合にのみ適用されます。

## <a name="set-up-a-microsoft-365-pilot"></a>Microsoft 365 パイロットをセットアップする

次の手順に従って、Microsoft 365 パイロットをセットアップします。

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターにサインインする

1. 職場または学校のアカウントで 「[Microsoft 365 管理センター](https://admin.microsoft.com)」にサインインします。

2. 左側のナビゲーションウィンドウで[**設定** > **ドメイン**]を選択します。

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>手順 2: 使おうとしているドメインを所有していることを確認する

1. [**ドメイン**] ページで、[**ドメインの追加**] を選択します。

2. ボックスにドメイン名を入力し、[**このドメインを使用**]を選択して、[**続行**]を選択します。

3. 電子メールやインスタントメッセージなど、ドメインでテストするサービスを選択します。

4. [**ドメインの確認**]ページで、手順バイ手順の指示に従い、次に[**確認**]を選択します。

    DNS の変更が有効になるまで数分から 72 時間かかります。

    確認が成功すると、DNS レコードを変更するように求められます。

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>手順 3: Exchange Online でドメインを共有としてマークする

1. Exchange 管理センターの[**メールフロー**]セクションで、[**承認済みドメイン**]を選択してから、変更するドメインを選択します。

2. ダブルクリックしてウィンドウを開き、[**内部リレー**]を選択します。

3. [**保存**] を選択します。

    この設定が有効になるまでに数分かかる場合があります。

### <a name="step-4-unblock-the-existing-email-server-optional"></a>手順 4: 既存の電子メールサーバーのブロックを解除します（オプション）

Microsoft 365 では、スパム保護に Exchange Online Protection（EOP） を使用しています。 EOP は、現在のメールサーバーが転送する大量のスパムを検出すると、既存のメールサーバーをブロックする可能性があります。 他の電子メールプロバイダーのスパム保護を信頼している場合は、Microsoft 365でサーバーのブロックを解除できます。

> [!NOTE]
> 既存の電子メールサーバーのブロックを解除すると、元のサーバーを介して届くすべてのスパムが Microsoft 365 メールボックスに届くようになるため、Microsoft 365 がスパムをどの程度防止できるかを評価することはできません。

1. Exchange 管理センターのナビゲーションウィンドウで、[**保護**]を選択し、[**接続フィルタ**]を選択します。

2. [**IP許可リスト**]で **+** を選択し、現在の電子メールプロバイダのメールサーバー IP アドレスを追加します。

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>手順 5: ユーザー アカウントを作成して主要な (返信先) アドレスを設定する

1. Microsoft 365 管理センター の左側のナビゲーションで、[**ユーザー** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**アクティブユーザー**</a>]を選択します。

2. 2 つの既存のユーザーを追加して、2 つのテストアカウントを作成します。

    アカウントごとに、[**+ユーザーを追加**]を選択し、テストするパスワードの方法など、必要な情報を入力します。

    ユーザーの電子メールアドレスが同じであることを確認するには、[**ユーザー名**]フィールドがユーザーの現在の電子メールアドレスと一致していなければなりません。

3. 適切なライセンスを選択し、[**次へ**]をクリックして、[**追加の終了**]をクリックします。

4. [**ユーザー名**] の隣の、ドロップダウン リストからカスタム ドメイン名を選択します。

5. **を選択し、** > **を作成し、** を閉じます。

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a>手順 6: **Microsoft 365 または Office 365 からメール サーバーに流れるようにメールを構成する

次の 2 つの手順を実行します。

1. Microsoft 365 または Office 365 環境を構成します。

2. Microsoft 365 または Office 365 からメール サーバーへのコネクタを設定します。

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a>1. Microsoft 365 または Office 365 環境を構成する

Microsoft 365 または Office365 で次の手順が完了したことを確認してください。

1. コネクタを設定するには、開始する前にアクセス許可を割り当てる必要があります。 必要なアクセス許可を確認するには、「[Exchange Online の機能のアクセス許可](/exchange/permissions-exo/feature-permissions)」トピックの「Microsoft 365 および Office 365 コネクタ」の項目を参照してください。

2. EOP か ExchangeOnline でメール サーバーからインターネットにメールを中継する場合は、次のいずれかの方法を実行します。

   - Microsoft 365 または Office 365 の承認済みドメインと一致するサブジェクト名で構成されている証明書を使用します。 証明書の共通名、またはサブジェクトの別名を組織のプライマリ SMTP ドメインと一致させることをお勧めします。 詳細については、「[オンプレミスのメール環境の前提条件](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment)」を参照してください。

   または

   - 組織の送信者のドメインとサブドメインがすべて Microsoft 365 または Office 365 の承認済みドメインとして構成されていることを確認します。

   承認済みドメインの定義に関する詳細は、「[Exchange Online で承認済みドメインを管理する](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)」および「[Exchange Online でサブドメインのメール フローを有効にする](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains)」をご覧ください。

3. Microsoft 365 または Office 365 からメール サーバーへとメールを配信するのに、メール フロー ルール (トランスポート ルールとも呼ばれます) を使用するか、ドメイン名を使用するかを決定します。 ほとんどの企業は、すべての承認済みドメインにメールを配信することを選択します。 詳細については、「[シナリオ: Exchange Online での条件付きメール ルーティング](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing)」を参照してください。

> [!NOTE]
> 「[Exchange Online でのメール フロー ルールの処理](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)」の説明に従って、メール フロー ルールを設定できます。 たとえば、現在メールが配布リストを介して複数のサイトに送信されている場合は、コネクタ付きのメール フロー ルールを使用できます。

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a>2. Microsoft 365 または Office 365 からメール サーバーへのコネクタを設定します。

Microsoft 365 または Office 365 にコネクタを作成するには、**[管理者]** をクリックし、そして **[Exchange]** をクリックして Exchange 管理センターへ移動します。 次に、**[メール フロー]** をクリックし、**[コネクタ]** をクリックします。

ウィザードを使用してコネクタを設定します。

ウィザードを起動するには、プラス記号 **+** をクリックします。 最初の画面で、**From** Office 365 および **To** 組織のメール サーバーを選択します。

**[次へ]** をクリックして、ウィザードの指示に従います。 詳細情報については、**[ヘルプ]** または **[詳細情報]** リンクをクリックします。 ウィザードに従って設定を行います。 最後に、コネクタが検証されたことを確認します。 コネクタが検証されない場合は、表示されているメッセージをダブルクリックして詳細を表示させ、問題の解決のために「[コネクタを検証する](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors)」を参照します。



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a>手順 7: DNS ホスティング プロバイダーで DNS レコードを更新する

DNS ホスティングプロバイダーの Web サイトにサインインし、「[DNS レコードを追加してドメインに接続する](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)」の手順に従います。

**次の2つの例外を設けてください。**

- 新しい MX レコードは作成せず、既存の MX レコードの変更も行いません。

- Exchange Online の新しい SPF （TXT）レコードを作成する代わりに、以前の電子メールプロバイダーの Sender Policy Framework （SPF）レコードが既にある場合は、現在のTXTレコードに「include:spf.protection.outlook.com」を追加します。

    例えば、「v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all」です。

    SPF レコードがない場合は、Microsoft 365 が推奨するレコードに変更を加えて現在のメール プロバイダー用のドメインを含め、spf.protection.outlook.com も含めます。両方のメール システムからの送信メッセージが承認されます。

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a>手順 8: 現在のプロバイダーで電子メールの転送をセットアップする

現在の電子メール プロバイダーで、onmicrosoft.com domain ドメインへの転送を管理するユーザーの電子メール アカウントで設定します。

- ユーザー A メールボックスを usera@yourcompany.onmicrosoft.com に転送する

- ユーザー B のメールボックスをuserb@yourcompany.onmicrosoft.comに転送する

この手順を完了すると、usera@yourcompany.com および userb@yourcompany.com に送信されたすべての電子メールが Microsoft 365 で利用できるようになります。

> [!NOTE]
> 電子メール転送を設定する正確な手順については、現在の電子メールプロバイダーにお問い合わせください。<br/>
> 現在の電子メール プロバイダーでメッセージのコピーを保持する必要はありません。<br/>
> 大半のプロバイダーは、返信が元の送信者に送信されるように、送信者の返信先アドレスをそのままにして電子メールを転送します。

### <a name="step-9-test-mail-flow"></a>手順 9: メール フローをテストする

1. ユーザー A の資格情報を使用して Outlook Web App にサインインします。

2. 次のテストを実行します。

    - 例えば、ユーザー B に電子メールを送信して、ローカルのMicrosoft 電子メールをテストします。電子メールはすぐに配信されます。 このシナリオでは、Microsoft 365 メールボックスがローカルであるため、メッセージは元のサーバーのユーザー B のメールボックスにルーティングされません。

    - 例えば、ユーザー C に電子メールを送信して、既存の電子メールシステムのユーザーへの電子メールをテストします。電子メールは、元のメールサーバーのユーザー C のメールボックスに配信されます。

    - 外部アカウントまたは既存の電子メールシステムの従業員の電子メールアカウントから転送が正しく設定されていることを確認します。 例えば、ユーザー C の元のサーバーアカウントまたは Hotmail アカウントから、ユーザー A に電子メールを送信し、それがユーザー A の Microsoft 365 メールボックスに届くことを確認します。

### <a name="step-10-move-mailbox-contents"></a>手順 10: メールボックスのコンテンツを移動する

2 名のテストユーザーのみを移動し、ユーザー A とユーザー B の両方が Outlook を使用しているため、新しいOutlookプロファイルで古い .PST ファイルを開き、メッセージ、カレンダーアイテム、連絡先などをコピーすることで、電子メールを移動できます。  詳細については、「[Outlook の .pst ファイルからメール、連絡先、カレンダーをインポートする](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)」をご覧ください。

それらが Microsoft 365 メールボックスの適切な場所にインポートされると、アイテムはどこのどのデバイスからでもアクセスできるようになります。
