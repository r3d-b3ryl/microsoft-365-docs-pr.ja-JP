---
title: スタンドアロン EOP サービスをセットアップする
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
description: 管理者は、オンプレミスのメール環境を保護するようにスタンドアロン Exchange Online Protection (EOP) を設定する方法を学習できます。
ms.openlocfilehash: cf49cf4b0784731c23c0c36de44d3b0b2cb78dc8
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827823"
---
# <a name="set-up-your-standalone-eop-service"></a>スタンドアロン EOP サービスをセットアップする

ここでは、Exchange Online Protection (EOP) のスタンドアロン環境のセットアップ方法について説明します。 Office 365 ドメイン ウィザードからここに移動してきた場合、Exchange Online Protection を使用する必要がなければ Office 365 ドメイン ウィザードに戻ってください。 コネクタの構成方法の詳細については、「[Configure mail flow using connectors in Office 365](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」をご覧ください。

> [!NOTE]
> このトピックは、対象とする社内メールボックスがあり、それらをスタンドアロン シナリオとして知られている EOP で保護する場合を前提としています。 Exchange Online によりクラウド上のすべてのメールボックスをホストする場合、このトピックに記載されているすべての作業を行う必要はありません。 サインアップ [してクラウド メールボックスを購入するには、Exchange Online](https://products.office.com/exchange/compare-microsoft-exchange-online-plans) プランの比較に移動します。 社内メールボックスの一部をホストし、一部をクラウド上に置く場合は、ハイブリッド シナリオと呼びます。 この場合、より高度なメール フローの設定が必要です。 [Exchange Server展開では、](https://docs.microsoft.com/exchange/exchange-hybrid) ハイブリッド メール フローとその設定方法を示すリソースへのリンクが含まれています。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- このタスクの予想所要時間:1 時間

- これらの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 具体的には、リモートの役割と Accepted Domains 役割が必要です。この役割は、既定で MailFlowAdministrator および OrganizationManagement (全体管理者) 役割グループに割り当てられます。 詳細については、「スタンドアロン [EOP のアクセス許可」を参照し、EAC](feature-permissions-in-eop.md) [を使用して役割グループ内のメンバーの一覧を変更します](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)。

- EOP に登録にしていない場合は、「[Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection)」にアクセスして、サービスを購入するか、試用してみてください。

- このトピックの手順で使用可能なキーボード ショートカットについては [、Exchange Online の Exchange 管理センターのキーボード ショートカットを参照してください](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center)。

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351) フォーラムでサポートをご依頼ください。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>手順 1: Microsoft 365 管理センターを使用してドメインを追加して確認する

1. Microsoft [365 管理センターで、[セットアップ](https://docs.microsoft.com/microsoft-365/admin/admin-overview/about-the-admin-center)] に **移動して** サービスにドメインを追加します。

2. ドメインの所有権を確認するため、以下の手順に従って、適用可能な DNS レコードを DNS ホスティング プロバイダーに追加します。

> [!TIP]
> [Office 365 にドメインを追加して](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)[、Office 365](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)用の任意の DNS ホスティング プロバイダーで DNS レコードを作成すると、サービスにドメインを追加して DNS を構成する場合に参照しているリソースが役立ちます。

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>手順 2:受信者を追加し、オプションとして DBEB を有効化する

EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」に記載されているように、これを行うにはいくつかの方法があります。さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。DBEB の詳細については、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>手順 3:EAC を使用してメール フローをセットアップする

Exchange 管理センター (EAC) でコネクタを作成し、EOP とオンプレミスのメール サーバー間のメール フローを有効にします。 詳細な手順については [、「Microsoft 365 と独自の電子メール サーバーの間のメールをルーティングするようにコネクタを設定する」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)。

### <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法

サービスとユーザーの環境間のメール フローを確認します。 詳細については [、「Microsoft 365 コネクタを検証してメール フローをテストする」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>手順 4: 受信ポート 25 SMTP アクセスを許可する

コネクタを構成した後、DNS レコードの更新が伝達されるのを 72 時間待つ。 この後、ファイアウォールまたはメール サーバーで、EOP データセンターからの (具体的には [Exchange Online Protection の IP アドレス](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) に一覧表示されている IP アドレスからの) メールだけを受信するように、受信用ポート 25 の SMTP トラフィックを制限します。 これにより、受信可能な受信メッセージの範囲が制限され、社内環境が保護されます。 また、メール リレーへの接続が許可される IP アドレスを制御するようにメール サーバーを設定している場合は、その設定も更新します。

> [!TIP]
> SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。 この設定はほとんどの状況で使用できますが、たとえば、大きな添付ファイルを含むメッセージを送信した場合に、あるくらかの遅延をお勧めします。

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>手順 5: スパムがそれぞれのユーザーの [迷惑メール] フォルダーにルーティングされるかどうかを確認する

スパム (迷惑) メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。 ハイブリッド環境の迷惑メール [フォルダーにスパムを配信するためのスタンドアロン EOP を構成する手順を示します](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

メッセージをそれぞれのユーザーの迷惑メール フォルダーに移動しない場合は、スパム対策ポリシーを編集すると別のアクションを選択できます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>手順 6: Microsoft 365 管理センターを使用して、MX レコードが EOP をポイントするようにする

ドメイン構成手順に従って、ドメインの MX レコードを更新し、受信メールが EOP 経由で流れます。 サード パーティのフィルタリング サービスを通して電子メールを EOP に送るのではなく、MX レコードが直接 EOP をポイントするようにします。 詳細については、「[Office 365 の DNS レコードを作成する ](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider)」を参照してください。

> [!NOTE]
> EOP の前面に存在する別のサーバーまたはサービスを MX レコードで参照する必要がある場合は [、Exchange Online の「コネクタの拡張フィルター処理」を参照してください](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

### <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法

ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。

- サービスとユーザーの環境間のメール フローを確認します。 詳細については [、「Microsoft 365 コネクタを検証してメール フローをテストする」を参照してください](https://docs.microsoft.com/exchange/mail-flow-best-practices/test-mail-flow)。

- Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。

- 送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。

> [!TIP]
> セットアップが完了したら、EOP がスパムやマルウェアを削除するために追加の手順を実行する必要はありません。 EOP はスパムやマルウェアを自動的に削除します。 ただし、ビジネス要件に基づいて設定を詳細に変更できます。 詳細については [、「Office 365 のスパム対策とマルウェア対策の保護」と「スプーフィング](anti-spam-and-anti-malware-protection.md) インテリジェン [スの構成」を参照してください](learn-about-spoof-intelligence.md)。 <br/><br/> サービスが実行されたので、EOP の構成に関するベスト プラクティスを読む [ことをお勧めします。これは、EOP](best-practices-for-configuring-eop.md)のセットアップ後の推奨設定と考慮事項について説明しています。
