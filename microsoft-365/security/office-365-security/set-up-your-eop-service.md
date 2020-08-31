---
title: スタンドアロンの EOP サービスをセットアップする
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: 管理者は、スタンドアロンの Exchange Online Protection (EOP) をセットアップしてオンプレミスの電子メール環境を保護する方法について説明します。
ms.openlocfilehash: e6ca3965dd82bf0e6ed7e361984758ab34e3eea0
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307593"
---
# <a name="set-up-your-standalone-eop-service"></a>スタンドアロンの EOP サービスをセットアップする

このトピックでは、スタンドアロンの Exchange Online Protection (EOP) を設定する方法について説明します。 Office 365 ドメイン ウィザードからここに移動してきた場合、Exchange Online Protection を使用する必要がなければ Office 365 ドメイン ウィザードに戻ってください。 コネクタの構成方法の詳細については、「[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」をご覧ください。

> [!NOTE]
> このトピックは、対象とする社内メールボックスがあり、それらをスタンドアロン シナリオとして知られている EOP で保護する場合を前提としています。 Exchange Online によりクラウド上のすべてのメールボックスをホストする場合、このトピックに記載されているすべての作業を行う必要はありません。 「 [Exchange Online プランの比較](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) 」に移動して、クラウドメールボックスをサインアップして購入します。 社内メールボックスの一部をホストし、一部をクラウド上に置く場合は、ハイブリッド シナリオと呼びます。 この場合、より高度なメール フローの設定が必要です。 「 [Exchange Server のハイブリッド展開](https://docs.microsoft.com/exchange/exchange-hybrid)」には、ハイブリッドメールフローについての説明と、設定方法を示すリソースへのリンクがあります。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- このタスクの予想所要時間:1 時間

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、既定では、[リモートドメインと承認済みドメイン] の役割が必要です。これは、既定では、MailFlowAdministrator および組織の管理 (グローバル管理者) の役割グループに割り当てられます。 詳細については、「 [Permissions in STANDALONE EOP](feature-permissions-in-eop.md) 」を参照して、EAC を使用して、 [役割グループのメンバーの一覧を変更](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)します。

- EOP に登録にしていない場合は、「[Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection)」にアクセスして、サービスを購入するか、試用してみてください。

- このトピックの手順に適用されるキーボードショートカットについては、「exchange [Online の exchange 管理センターのキーボードショートカット](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)」を参照してください。

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>手順 1: Microsoft 365 管理センターを使用してドメインを追加して確認する

1. [Microsoft 365 管理センター](https://docs.microsoft.com/microsoft-365/admin/admin-overview/about-the-admin-center)で、[**セットアップ**] を使用して、ドメインをサービスに追加します。

2. ドメインの所有権を確認するため、以下の手順に従って、適用可能な DNS レコードを DNS ホスティング プロバイダーに追加します。

> [!TIP]
> Office [365 にドメインを追加](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)して、[任意の dns ホスティングプロバイダーで office 365 用の Dns レコードを作成](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)することは、ドメインをサービスに追加して dns を構成する際に参照するのに便利なリソースです。

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>手順 2:受信者を追加し、オプションとして DBEB を有効化する

EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」に記載されているように、これを行うにはいくつかの方法があります。さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。DBEB の詳細については、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>手順 3:EAC を使用してメール フローをセットアップする

Exchange 管理センター (EAC) でコネクタを作成し、EOP とオンプレミスのメール サーバー間のメール フローを有効にします。 詳細な手順については、「 [Microsoft 365 と独自の電子メールサーバーの間でメールをルーティングするようにコネクタを設定する](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)」を参照してください。

### <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法

サービスと環境の間のメールフローをチェックします。 詳細については、「 [Microsoft 365 コネクタを検証することによるメールフローのテスト](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)」を参照してください。

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>手順 4: 受信ポート 25 SMTP アクセスを許可する

コネクタを構成したら、72時間待機して、DNS レコードの更新を反映できるようにします。 この後、ファイアウォールまたはメール サーバーで、EOP データセンターからの (具体的には [Exchange Online Protection の IP アドレス](https://docs.microsoft.com/microsoft-365/enterprise/urls-and-ip-address-ranges) に一覧表示されている IP アドレスからの) メールだけを受信するように、受信用ポート 25 の SMTP トラフィックを制限します。 これにより、受信可能な受信メッセージの範囲が制限され、社内環境が保護されます。 また、メール リレーへの接続が許可される IP アドレスを制御するようにメール サーバーを設定している場合は、その設定も更新します。

> [!TIP]
> SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。 この設定は、大規模な添付ファイルで送信されたメッセージの場合など、遅延が発生する場合がほとんどの場合に使用できます。

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>手順 5: スパムが各ユーザーの迷惑メールフォルダーにルーティングされるようにする

スパム (迷惑) メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。 この手順は、 [ハイブリッド環境の迷惑メールフォルダーにスパムを配信するように、[スタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)] で提供されています。

各ユーザーの迷惑メールフォルダーにメッセージを移動しない場合は、スパム対策ポリシーを編集して別のアクションを選択することができます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>手順 6: Microsoft 365 管理センターを使用して MX レコードを EOP にポイントする

ドメイン構成手順に従って、受信メールが EOP を通過するように、ドメインの MX レコードを更新します。 サード パーティのフィルタリング サービスを通して電子メールを EOP に送るのではなく、MX レコードが直接 EOP をポイントするようにします。 詳細については、「[Office 365 の DNS レコードを作成する ](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」を参照してください。

> [!NOTE]
> MX レコードが EOP の前にある別のサーバーまたはサービスを指している必要がある場合は、「 [Exchange Online のコネクタの拡張フィルター処理](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)」を参照してください。

### <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法

ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。

- サービスと環境の間のメールフローをチェックします。 詳細については、「 [Microsoft 365 コネクタを検証することによるメールフローのテスト](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)」を参照してください。

- Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。

- 送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。

> [!TIP]
> セットアップが完了したら、EOP を使用してスパムやマルウェアを削除するために、特別な手順を実行する必要はありません。 EOP はスパムやマルウェアを自動的に削除します。 ただし、ビジネス要件に基づいて設定を微調整することができます。 詳細については、「 [Office 365 のスパム対策およびマルウェア対策保護](anti-spam-and-anti-malware-protection.md) 」および「 [Configure スプーフ知能](learn-about-spoof-intelligence.md)」を参照してください。 <br/><br/> サービスが実行されたので、 [EOP を構成するためのベストプラクティス](best-practices-for-configuring-eop.md)を読み取ることをお勧めします。これは、EOP のセットアップ後に推奨される設定と考慮事項について説明します。
