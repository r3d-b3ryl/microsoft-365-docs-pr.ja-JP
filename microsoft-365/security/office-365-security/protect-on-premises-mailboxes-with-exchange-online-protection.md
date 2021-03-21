---
title: スタンドアロン EOP を使用して、中国のオンプレミスのメールボックスを保護する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- GEU150
- GMA150
- GPA150
- MET150
ms.assetid: c5e95951-da67-4ec7-92c5-982abd477e69
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 21Vianet がOffice 365 を使用する中国の管理者は、スタンドアロンの Exchange Online Protection (EOP) を使用してオンプレミスのメールボックスを保護する方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4258d64721fc2042297bb15eaeecafa90dcf4bc1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929290"
---
# <a name="protect-on-premises-mailboxes-in-china-with-standalone-eop"></a>スタンドアロン EOP を使用して、中国のオンプレミスのメールボックスを保護する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> この記事は、中国Office 21Vianet が運営する 365 のバージョンにのみ適用されます。

一部またはすべてのメールボックスをオンプレミスでホストする予定の場合でも、Exchange Online Protection (EOP) を使用してメールボックスを保護できます。 コネクタを構成するには、アカウントがグローバル管理者または Exchange Company Administrator (組織の管理役割グループ) である必要があります。 365 アクセス許可Office Exchange アクセス許可とどのように関連付けるかについては [、「21Vianet](../../admin/add-users/assign-admin-roles.md?preserve-view=true&view=o365-21vianet)が運用する Office 365 での管理者ロールの割り当て」を参照してください。 すべての Exchange メールボックスがオンプレミスの場合は、次の手順に従って EOP サービスをセットアップします。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>手順 1: Microsoft 365 管理センターを使用してドメインを追加および確認する

1. Microsoft 365 管理センターで、[セットアップ] に移動して、ドメインをサービスに追加します。

2. ドメインの所有権を確認するには、ポータルの手順に従って該当する DNS レコードを DNS ホスティング プロバイダーに追加します。

> [!TIP]
> [21Vianet](../../admin/setup/add-domain.md?preserve-view=true&view=o365-21vianet) が運用する Office 365 にドメインとユーザーを追加し、DNS レコードを管理する際に [Office 365](../../admin/services-in-china/create-dns-records-when-you-manage-your-dns-records.md?preserve-view=true&view=o365-21vianet) の DNS レコードを作成すると、サービスにドメインを追加して DNS を構成するときに参照する際に役立つリソースになります。

### <a name="step-2-add-recipients-and-configure-the-domain-type"></a>手順 2: 受信者を追加し、ドメインの種類を構成する

EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。 「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」に記載されているように、これを行うにはいくつかの方法があります。 さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。 DBEB の詳細については [、「Use Directory Based Edge Blocking to reject messages to invalid recipients 」を参照してください](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)。

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>手順 3:EAC を使用してメール フローをセットアップする

Exchange 管理センター (EAC) でコネクタを作成し、EOP とオンプレミスのメール サーバー間のメール フローを有効にします。 詳細な手順については [、「Configure mail flow using connectors in Office 365」を参照してください](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)。

 このタスクの検証方法

 [「365 コネクタを検証してメール フロー Officeする」を参照してください](/exchange/mail-flow-best-practices/test-mail-flow)。

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>手順 4: 受信ポート 25 SMTP アクセスを許可する

コネクタを構成した後、DNS レコードの更新が伝達されるよう 72 時間待ちます。 この後、ファイアウォールまたはメール サーバー上の受信ポート 25 SMTP トラフィックを、EOP データセンターからのメールのみを受け入れる (特に、OFFICE [365](../../enterprise/managing-office-365-endpoints.md)の URL および IP アドレス範囲に記載されている IP アドレスから) 制限します。 これにより、受信可能な受信メッセージの範囲が制限され、社内環境が保護されます。 また、メール リレーへの接続が許可される IP アドレスを制御するようにメール サーバーを設定している場合は、その設定も更新します。

> [!TIP]
> SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。この設定はほとんどの状況で使用可能ですが、メッセージをサイズの大きな添付書類とともに送信した場合などに備えて、ある程度の遅延を設けてください。

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>手順 5: スパムが各ユーザーの迷惑メール フォルダーにルーティングされるのを確認する

スパム (迷惑) メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。 手順については、「スタンドアロン EOP を構成してハイブリッド環境の迷惑メール フォルダーにスパムを配信 [する」で説明します](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。 各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、スパム対策ポリシー (コンテンツ フィルター ポリシーとも呼ばれる) を編集して別のアクションを選択できます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>手順 6: Microsoft 365 管理センターを使用して MX レコードを EOP にポイントする

Office 365 ドメイン構成手順に従って、ドメインの MX レコードを更新し、受信メールが EOP 経由で流れるようにします。 詳細については、DNS レコードを管理するときに、Office [365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md?preserve-view=true&view=o365-21vianet)の DNS レコードの作成を参照できます。

このタスクの検証方法

 [「365 コネクタを検証してメール フロー Officeする」を参照してください](/exchange/mail-flow-best-practices/test-mail-flow)。

ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。

- リモート接続アナライザーで **[Office 365]** タブをクリックし、次に **[インターネット電子メールのテスト]** の下にある **[受信 SMTP 電子メール]** を実行します。

- Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。

- 送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。

## <a name="less-common-a-hybrid-setup-with-mailboxes-on-premises-and-in-the-cloud"></a>あまり一般的でなく:オンプレミスおよびクラウド内のメールボックスを使用したハイブリッド セットアップ

Exchange Online で Exchange メールボックスがオンプレミスで、クラウドに 1 つ以上のメールボックスがある場合は、ハイブリッドセットアップ *を行* います。 ハイブリッドセットアップでは、空き時間情報の予定表の共有やメール ルーティングなどの機能が、オンプレミス環境とクラウド環境で一緒に機能します。 メールボックスを Exchange Online に移行する際に、ハイブリッドセットアップが行なっている可能性があります。 ハイブリッド環境は、EOP スタンドアロン保護とは異なる方法でセットアップされます。

ハイブリッド シナリオを選択して、ほとんどの従業員にクラウドベースの電子メールを利用できます。 これを行う一方で、一部のメールボックスをオンプレミスでホストできます。たとえば、法務部門の場合などです。

ハイブリッドセットアップは複雑な場合がありますが、多くの利点があります。 Exchange を使用したハイブリッド シナリオのセットアップの詳細については、「ハイブリッド展開のExchange Server [を参照してください](/Exchange/exchange-hybrid)。