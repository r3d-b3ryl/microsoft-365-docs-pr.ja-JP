---
title: スタンドアロン EOP サービスのセットアップ
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
ms.assetid: d74c6ddf-11b0-43ee-b298-8bb0340895f0
description: 管理者は、オンプレミスの電子メール環境を保護するためにスタンドアロン Exchange Online Protection (EOP) をセットアップする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bbad39475f87be27a83edc0c27e2bbe46f8e39ac
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206830"
---
# <a name="set-up-your-standalone-eop-service"></a>スタンドアロン EOP サービスのセットアップ

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
-  [Exchange Online Protectionスタンドアロン](exchange-online-protection-overview.md)

このトピックでは、スタンドアロン デバイス (EOP) をExchange Online Protectionについて説明します。 Office 365 ドメイン ウィザードからここに移動してきた場合、Exchange Online Protection を使用する必要がなければ Office 365 ドメイン ウィザードに戻ってください。 コネクタの構成方法の詳細については、「[Configure mail flow using connectors in Office 365](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow)」をご覧ください。

> [!NOTE]
> このトピックは、対象とする社内メールボックスがあり、それらをスタンドアロン シナリオとして知られている EOP で保護する場合を前提としています。 クラウド内のすべてのメールボックスを Exchange Online でホストする場合は、この記事のすべての手順を完了する必要があります。 [クラウド メールボックス[のExchange Online購入](https://products.office.com/exchange/compare-microsoft-exchange-online-plans)するプランを比較する] に移動します。
>
> 社内メールボックスの一部をホストし、一部をクラウド上に置く場合は、ハイブリッド シナリオと呼びます。 この場合、より高度なメール フローの設定が必要です。 [Exchange Serverハイブリッド展開では](/exchange/exchange-hybrid)、ハイブリッド メール フローについて説明し、それを設定する方法を示すリソースへのリンクがあります。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- このタスクの予想所要時間:1 時間

- この記事の手順を実行するには、Exchange Online Protectionにアクセス許可を割り当てる必要があります。 具体的には、既定で組織の管理 **(グローバル** 管理者) および Mail Flow 管理者役割グループに割り当てられているリモート ドメインと承諾 **ドメイン** の役割が必要です。 詳細については、「スタンドアロン [EOP のアクセス](feature-permissions-in-eop.md) 許可」および「役割グループのメンバーの一覧を [変更する EAC](manage-admin-role-group-permissions-in-eop.md#use-the-eac-modify-the-list-of-members-in-role-groups)を使用する」を参照してください。

- EOP に登録にしていない場合は、「[Exchange Online Protection](https://products.office.com/exchange/exchange-email-security-spam-protection)」にアクセスして、サービスを購入するか、試用してみてください。

- この記事の手順 Exchangeに適用されるキーボード ショートカットの詳細については、「Exchange Online の管理センターのキーボード ショートカット」[を参照Exchange Online。](/Exchange/accessibility/keyboard-shortcuts-in-admin-center)

> [!TIP]
> 問題が発生する場合 [Exchange Online Protection](https://social.technet.microsoft.com/Forums/forefront/home?forum=FOPE) フォーラムでサポートをご依頼ください。

## <a name="step-1-use-the-microsoft-365-admin-center-to-add-and-verify-your-domain"></a>手順 1: 管理者センター Microsoft 365を使用してドメインを追加および確認する

1. 管理センター [Microsoft 365[](../../admin/admin-overview/about-the-admin-center.md)セットアップ] に **移動して、** ドメインをサービスに追加します。

2. ドメインの所有権を確認するため、以下の手順に従って、適用可能な DNS レコードを DNS ホスティング プロバイダーに追加します。

> [!TIP]
> [ドメインを](../../admin/setup/add-domain.md)Office 365 に追加し[、Office 365](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)用の任意の DNS ホスティング プロバイダーで DNS レコードを作成すると、サービスにドメインを追加し、DNS を構成する場合に参照に役立ちます。

## <a name="step-2-add-recipients-and-optionally-enable-dbeb"></a>手順 2:受信者を追加し、オプションとして DBEB を有効化する

EOP サービスとの間のメール フローを設定する前に、受信者をサービスに追加することお勧めします。「[EOP でメール ユーザーを管理する](manage-mail-users-in-eop.md)」に記載されているように、これを行うにはいくつかの方法があります。さらに、受信者を追加した後にサービス内で受信者の検証を行うために、ディレクトリ ベースのエッジ ブロック (Directory Based Edge Blocking (DBEB)) を有効にする場合、ドメインの種類を [権限あり] に設定する必要があります。DBEB の詳細については、「[Use Directory Based Edge Blocking to Reject Messages Sent to Invalid Recipients](/exchange/mail-flow-best-practices/use-directory-based-edge-blocking)」を参照してください。

## <a name="step-3-use-the-eac-to-set-up-mail-flow"></a>手順 3:EAC を使用してメール フローをセットアップする

Exchange 管理センター (EAC) でコネクタを作成し、EOP とオンプレミスのメール サーバー間のメール フローを有効にします。 詳細な手順については、「コネクタをセットアップして、ユーザーと自分の電子メール Microsoft 365間でメールをルーティングする」[を参照してください](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail)。

### <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法

サービスと環境の間のメール フローを確認します。 詳細については、「Test [mail flow by validating your](/exchange/mail-flow-best-practices/test-mail-flow)Microsoft 365 コネクタ 」 を参照してください。

## <a name="step-4-allow-inbound-port-25-smtp-access"></a>手順 4: 受信ポート 25 SMTP アクセスを許可する

コネクタを構成した後、72 時間待って DNS レコード更新プログラムの伝達を許可します。 この後、ファイアウォールまたはメール サーバーで、EOP データセンターからの (具体的には [Exchange Online Protection の IP アドレス](../../enterprise/urls-and-ip-address-ranges.md) に一覧表示されている IP アドレスからの) メールだけを受信するように、受信用ポート 25 の SMTP トラフィックを制限します。 これにより、受信可能な受信メッセージの範囲が制限され、社内環境が保護されます。 また、メール リレーへの接続が許可される IP アドレスを制御するようにメール サーバーを設定している場合は、その設定も更新します。

> [!TIP]
> SMTP サーバーの設定を、60 秒で接続タイムアウトが発生するように構成します。 この設定はほとんどの状況で受け入れ可能です。たとえば、添付ファイルが大きいメッセージが送信された場合に遅延が発生する可能性があります。

## <a name="step-5-ensure-that-spam-is-routed-to-each-users-junk-email-folder"></a>手順 5: スパムが各ユーザーの迷惑メール フォルダーにルーティングされるのを確認する

スパム (迷惑) メールがそれぞれのユーザーの迷惑メール フォルダーに正しくルーティングされることを保証するには、一組の構成手順を実行する必要があります。 手順については、「スタンドアロン EOP を構成してハイブリッド環境の迷惑メール フォルダーにスパムを配信 [する」で説明します](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)。

各ユーザーの迷惑メール フォルダーにメッセージを移動しない場合は、スパム対策ポリシーを編集して別のアクションを選択できます。 詳細については、「[Office 365 でのスパム対策ポリシーの構成](configure-your-spam-filter-policies.md)」を参照してください。

## <a name="step-6-use-the-microsoft-365-admin-center-to-point-your-mx-record-to-eop"></a>手順 6: 管理センター Microsoft 365使用して MX レコードを EOP にポイントする

ドメイン構成の手順に従ってドメインの MX レコードを更新し、受信メールが EOP を経由して流れます。 サード パーティのフィルタリング サービスを通して電子メールを EOP に送るのではなく、MX レコードが直接 EOP をポイントするようにします。 詳細については、「[Office 365 の DNS レコードを作成する ](../../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)」を参照してください。

> [!NOTE]
> MX レコードを EOP の前にある別のサーバーまたはサービスにポイントする必要がある場合は、「拡張フィルター for Connectors in Exchange Online」[を参照してください](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

### <a name="how-do-you-know-this-task-worked"></a>このタスクの検証方法

ここまでに、適切に構成された社内送信コネクタのサービス配信の検証と、MX レコードが EOP を指していることの検証が完了しました。次に、電子メールがサービスによって社内環境に正常に配信されることを検証する、以下の追加テストの実行を選択します。

- サービスと環境の間のメール フローを確認します。 詳細については、「Test [mail flow by validating your](/exchange/mail-flow-best-practices/test-mail-flow)Microsoft 365 コネクタ 」 を参照してください。

- Web に基づく電子メール アカウントから、ドメインがサービスに追加したドメインと一致する、組織内のメール受信者に電子メール メッセージを送信します。Microsoft Outlook または別の電子メール クライアントを使って、社内メールボックスへのメッセージの配信を確認します。

- 送信電子メールのテストを実行する場合は、組織内のユーザーから Web ベースの電子メール アカウントに電子メールを送信し、メッセージが受信されたかを確認できます。

> [!TIP]
> セットアップが完了したら、EOP でスパムやマルウェアを削除するための追加の手順を実行する必要がなされません。 EOP はスパムやマルウェアを自動的に削除します。 ただし、ビジネス要件に基づいて設定を微調整できます。 詳細については、「スパム対策とマルウェア対策の保護」および「スプーフィング インテリジェンスの構成[」Office 365](anti-spam-and-anti-malware-protection.md)を[参照してください](learn-about-spoof-intelligence.md)。
>
> サービスが実行されたので [、EOP](best-practices-for-configuring-eop.md)を設定した後の推奨設定と考慮事項について説明する EOP の構成に関するベスト プラクティスを参照することをお勧めします。