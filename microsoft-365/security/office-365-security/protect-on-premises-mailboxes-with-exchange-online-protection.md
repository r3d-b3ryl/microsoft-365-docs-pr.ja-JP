---
title: Exchange Online Protection を使用して社内のメールボックスを保護する
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 6/1/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
description: 一部またはすべてのメールボックスを社内でホストすることを計画している場合でも、Exchange Online Protection (EOP) を使用してメールボックスを保護することができます。 コネクタを構成するには、アカウントが Office 365 グローバル管理者または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。 Office 365 のアクセス許可と Exchange のアクセス許可との関係の詳細については、「365 Office 2013 で運用されている管理者ロールの割り当て」を参照してください。 すべての Exchange メールボックスがオンプレミスである場合は、次の手順に従って EOP サービスを設定します。
ms.openlocfilehash: 8ff2e28100a748e34b8f079292d937cc9b3857e8
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895289"
---
# <a name="protect-on-premises-mailboxes-with-exchange-online-protection"></a>Exchange Online Protection を使用して社内のメールボックスを保護する

> [!NOTE]
> この記事は、中国で21Vianet が運営する Office 365 にのみ適用されます。

一部またはすべてのメールボックスを社内でホストすることを計画している場合でも、Exchange Online Protection (EOP) を使用してメールボックスを保護することができます。 コネクタを構成するには、アカウントが Office 365 グローバル管理者または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。 Office 365 のアクセス許可と Exchange のアクセス許可との関係の詳細については、「 [365 office 2013 で運用されている管理者ロールの割り当て](https://docs.microsoft.com/office365/admin/add-users/assign-admin-roles?&view=o365-21vianet)」を参照してください。 すべての Exchange メールボックスがオンプレミスである場合は、次の手順に従って EOP サービスを設定します。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>手順 1: Microsoft 365 管理センターを使用してドメインを追加して確認する

1. Microsoft 365 管理センターで、[セットアップ] に移動して、ドメインをサービスに追加します。

2. ポータルの手順に従って、ドメインの所有権を確認するために、該当する dns レコードを DNS ホストプロバイダーに追加します。

> [!TIP]
> 「 [21vianet が運用する office 365 にドメインとユーザーを追加](https://docs.microsoft.com/office365/admin/setup/add-domain?&view=o365-21vianet)する」と「 [365 office の Dns レコードを作成](https://docs.microsoft.com/office365/admin/services-in-china/create-dns-records-when-you-manage-your-dns-records?&view=o365-21vianet)する」を参照してください。 dns レコードを管理するときは、ドメインをサービスに追加して dns を構成する際に参照するのに役立つリソースです。

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>手順 2: 受信者を追加してドメインの種類を構成する

EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。 「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」に記載されているように、これを行うにはいくつかの方法があります。 さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。 DBEB の詳細については、「[ディレクトリベースのエッジブロックを使用して無効な受信者に送信されたメッセージを拒否する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>手順 3:EAC を使用してメール フローをセットアップする

Exchange 管理センター (EAC) でコネクタを作成し、EOP とオンプレミスのメール サーバー間のメール フローを有効にします。 詳細な手順については、「 [Configure mail flow using connector Using Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」を参照してください。

 このタスクの検証方法

 「 [Office 365 のコネクタを検証する」の「テストメールフロー」を](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)参照してください。

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>手順 4: 受信ポート 25 SMTP アクセスを許可する

コネクタを構成した後、DNS レコードの更新が伝達されるよう 72 時間待ちます。 次に、ファイアウォールまたはメールサーバーで受信ポート-25 の SMTP トラフィックを制限して、EOP データセンターからのメールのみを受け入れるようにします。具体的には、 [Office 365 の url および ip アドレス範囲](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)に記載されている ip アドレスからのみを受信します。 これにより、受信可能な受信メッセージの範囲が制限され、社内環境が保護されます。 また、メール リレーへの接続が許可される IP アドレスを制御するようにメール サーバーを設定している場合は、その設定も更新します。

> [!TIP]
> SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。この設定はほとんどの状況で使用可能ですが、メッセージをサイズの大きな添付書類とともに送信した場合などに備えて、ある程度の遅延を設けてください。

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>手順 5: スパムが各ユーザーの迷惑メールフォルダーにルーティングされるようにする

スパム (迷惑) メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。 この手順は、[ハイブリッド環境の迷惑メールフォルダーにスパムを配信するように、[スタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)] で提供されています。 メッセージをそれぞれのユーザーの迷惑メール フォルダーに移動しない場合は、Exchange 管理センターでコンテンツ フィルター ポリシーを編集すると別のアクションを選択できます。 詳細については、「 [Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>手順 6: Microsoft 365 管理センターを使用して MX レコードを EOP にポイントする

Office 365 ドメイン構成手順に従って、ドメインの MX レコードを更新し、受信メールが EOP 経由で流れるようにします。 詳細については、「DNS レコードを[管理するときに、Office 365 の dns レコードを作成](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)する」を参照してください。

このタスクの検証方法

 「 [Office 365 のコネクタを検証する」の「テストメールフロー」を](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)参照してください。

ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。

- リモート接続アナライザーで **[Office 365]** タブをクリックし、次に **[インターネット電子メールのテスト]** の下にある **[受信 SMTP 電子メール]** を実行します。

- Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。

- 送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>あまり一般的ではない: オンプレミスのメールボックスとクラウド内のハイブリッドセットアップ

Exchange Online で Exchange メールボックスがオンプレミスにあり、クラウド内に1つ以上のメールボックスがある場合は、*ハイブリッド*セットアップがあります。 ハイブリッドセットアップでは、オンプレミス環境とクラウド環境で、空き時間情報予定表共有やメールルーティングなどの機能が一緒に機能します。 メールボックスを Exchange Online に移行する際に、ハイブリッドセットアップが行われている場合があります。 ハイブリッド環境は、EOP スタンドアロンの保護とは異なる方法で設定されます。

多くの従業員に対してクラウドベースの電子メールを活用するために、ハイブリッドシナリオを選択することができます。 この操作は、オンプレミスのメールボックスの一部をホストするときに実行することもできます。たとえば、法務部門の場合です。

ハイブリッドセットアップは複雑になることがありますが、多くの利点があります。 Exchange を使用したハイブリッドシナリオのセットアップの詳細については、「 [Exchange Server のハイブリッド展開](https://docs.microsoft.com/Exchange/exchange-hybrid)」を参照してください。
