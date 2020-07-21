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
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: 2つのテストアカウントのみを使用して、カスタムドメインから Microsoft 365 メールボックスに電子メール機能をパイロットする方法について説明します。
ms.openlocfilehash: bfcb2bda4d560ab629ddebed88ac1d55e6224c05
ms.sourcegitcommit: 5f980a9eb5aca61cf3662ef0bc65dec215e21656
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/20/2020
ms.locfileid: "45186049"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>カスタムドメインから Microsoft 365 をパイロットする

次の要件と制限を使用して Microsoft 365 をパイロットできます。

- 現在の電子メール プロバイダーで、電子メール転送のサービスが提供されている必要があります。

- Microsoft 365 にこれらのレコードを管理させるのではなく、DNS ホスティングプロバイダーでMicrosoft 365 DNS レコードを管理する必要があります。

    詳細については、「[DNSレコードを追加してドメインに接続する](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」をご覧ください。

- 他の電子メールサーバーのユーザーの空き時間情報は利用できません。

- 管理者が 1 つの場所からすべてのユーザーアカウントを管理することはできません。

- ユーザーが Microsoft 365 スパムフィルターを使用できない場合があります。

## <a name="set-up-a-microsoft-365-pilot"></a>Microsoft 365 パイロットをセットアップする

次の手順に従って、Microsoft 365 パイロットをセットアップします。

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>手順 1: Microsoft 365 管理センターにサインインする

1. 職場または学校のアカウントで 「[Microsoft 365 管理センター](https://admin.microsoft.com)」にサインインします。

2. 左側のナビゲーションウィンドウで[**設定** > **ドメイン**]を選択します。

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>手順 2: 使おうとしているドメインを所有していることを確認する

1. [**ドメイン**] ページで、[**ドメインの追加**] を選択します。

2. ボックスにドメイン名を入力し、[**このドメインを使用**]を選択して、[**続行**]を選択します。

3. 電子メールやインスタントメッセージなど、ドメインでテストするサービスを選択します。

5. [**ドメインの確認**]ページで、手順バイ手順の指示に従い、次に[**確認**]を選択します。

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

2. [**IP許可リスト**]で**+** を選択し、現在の電子メールプロバイダのメールサーバー IP アドレスを追加します。 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>手順 5: ユーザー アカウントを作成して主要な (返信先) アドレスを設定する

1. Microsoft 365 管理センターの左側のナビゲーションで、[**ユーザー** > **アクティブユーザー**]を選択します。

2. 2 つの既存のユーザーを追加して、2 つのテストアカウントを作成します。

    アカウントごとに、[** +ユーザーを追加**]を選択し、テストするパスワードの方法など、必要な情報を入力します。

    ユーザーの電子メールアドレスが同じであることを確認するには、[**ユーザー名**]フィールドがユーザーの現在の電子メールアドレスと一致していなければなりません。

3. 適切なライセンスを選択し、[**次へ**]をクリックして、[**追加の終了**]をクリックします。 

4. [**ユーザー名**] の隣の、ドロップダウン リストからカスタム ドメイン名を選択します。 

5. **を選択し、** > **を作成し、** を閉じます。

### <a name="step-6-update-dns-records-at-your-dns-hosting-provider"></a>手順 6: DNS ホスティング プロバイダーで DNS レコードを更新する

DNS ホスティングプロバイダーの Web サイトにサインインし、「[DNS レコードを追加してドメインに接続する](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」の手順に従います。

**次の2つの例外を設けてください。**

- 新しい MX レコードは作成せず、既存の MX レコードの変更も行いません。

- Exchange Online の新しい SPF （TXT）レコードを作成する代わりに、以前の電子メールプロバイダーの Sender Policy Framework （SPF）レコードが既にある場合は、現在のTXTレコードに「include:spf.protection.outlook.com」を追加します。

    例えば、「v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all」です。

    SPFレコードがない場合は、Microsoft 365 で推奨されているレコードを変更して、現在の電子メールプロバイダーのドメインを含め、spf.protection.outlook.com を追加します。 これにより、両方の電子メールシステムからの送信メッセージが承認されます。

### <a name="step-7-set-up-email-forwarding-at-your-current-provider"></a>手順 7: 現在のプロバイダーで電子メールの転送をセットアップする

現在の電子メール プロバイダーで、onmicrosoft.com domain ドメインへの転送を管理するユーザーの電子メール アカウントで設定します。

- ユーザー A メールボックスを usera@yourcompany.onmicrosoft.com に転送する

- ユーザー B のメールボックスをuserb@yourcompany.onmicrosoft.comに転送する

この手順を完了すると、usera@yourcompany.com および userb@yourcompany.com に送信されたすべての電子メールが Microsoft 365 で利用できるようになります。

> [!NOTE]
> 電子メール転送を設定する正確な手順については、現在の電子メールプロバイダーにお問い合わせください。<br/>
> 現在の電子メール プロバイダーでメッセージのコピーを保持する必要はありません。<br/>
> 大半のプロバイダーは、返信が元の送信者に送信されるように、送信者の返信先アドレスをそのままにして電子メールを転送します。

### <a name="step-8-test-mail-flow"></a>手順 8: メール フローをテストする

1. ユーザー A の資格情報を使用して Outlook Web App にサインインします。

2. 次のテストを実行します。

    - 例えば、ユーザー B に電子メールを送信して、ローカルのMicrosoft 電子メールをテストします。電子メールはすぐに配信されます。 このシナリオでは、Microsoft 365 メールボックスがローカルであるため、メッセージは元のサーバーのユーザー B のメールボックスにルーティングされません。

    - 例えば、ユーザー C に電子メールを送信して、既存の電子メールシステムのユーザーへの電子メールをテストします。電子メールは、元のメールサーバーのユーザー C のメールボックスに配信されます。

    - 外部アカウントまたは既存の電子メールシステムの従業員の電子メールアカウントから転送が正しく設定されていることを確認します。 例えば、ユーザー C の元のサーバーアカウントまたは Hotmail アカウントから、ユーザー A に電子メールを送信し、それがユーザー A の Microsoft 365 メールボックスに届くことを確認します。

### <a name="step-9-move-mailbox-contents"></a>手順 9: メールボックスのコンテンツを移動する

2 名のテストユーザーのみを移動し、ユーザー A とユーザー B の両方が Outlook を使用しているため、新しいOutlookプロファイルで古い .PST ファイルを開き、メッセージ、カレンダーアイテム、連絡先などをコピーすることで、電子メールを移動できます。  詳細については、「[Outlook の .pst ファイルからメール、連絡先、カレンダーをインポートする](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac)」をご覧ください。

それらが Microsoft 365 メールボックスの適切な場所にインポートされると、アイテムはどこのどのデバイスからでもアクセスできるようになります。

より多くのメールボックスが関係する場合、または従業員が Outlook を使用していない場合は、Exchange 管理センターで利用可能な移行ツールを使用できます。 開始するには、Exchange 管理センターに移動し、[IMAP サーバーから Exchange Online メールボックスへのメールの移行-新しい記事のリソースが必要です]の指示に従います。