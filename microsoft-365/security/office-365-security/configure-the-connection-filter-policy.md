---
title: 既定の接続フィルター ポリシーを構成する
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、電子メール サーバーからのメールを許可またはブロックするために、Exchange Online Protection (EOP) で接続フィルターを構成する方法について学習できます。
ms.openlocfilehash: 45213ff36c7efc76a83a2c520e0369211ffecf53
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827847"
---
# <a name="configure-connection-filtering"></a>接続フィルターの構成

Exchange Online のメールボックスを使用している Microsoft 365 のお客様、または Exchange Online のメールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) をお使いのお客様の場合は、EOP の接続フィルター (具体的には既定の接続フィルター ポリシー) を使用して、IP アドレスに基づいて良好なまたは不適切な送信元の電子メール サーバーを特定します。 既定の接続フィルター ポリシーの主な構成要素は次のとおりです。

- **IP 許可一覧**: IP アドレスまたは IP アドレス範囲で指定した送信元の電子メール サーバーからのすべての受信メッセージに対して、スパム フィルターをスキップします。 これらのソースからのメッセージにスパム フィルターが引き続き発生する可能性があるシナリオについては、このトピックの [後半にある「IP 許可](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 一覧のソースからのメッセージ」でフィルター処理が実行されるシナリオを参照してください。 IP 許可一覧を信頼できる差出人の全体的な戦略にどのようにして適用するかについては [、「EOP で信頼できる送信者リストを作成する」を参照してください](create-safe-sender-lists-in-office-365.md)。

- **IP 禁止一覧**: IP アドレスまたは IP アドレス範囲で指定した送信元メール サーバーからの受信メッセージをすべてブロックする。 受信メッセージは拒否され、スパムとしてマークされなく、追加のフィルター処理は行いません。 受信拒否リスト全体に IP 禁止一覧を設定する方法の詳細については、「EOP で受信 [拒否リストを作成する」を参照してください](create-block-sender-lists-in-office-365.md)。

- **セーフ**リスト : セ *ーフ リスト* は、ユーザーによる設定が必要な Microsoft データセンター内の動的許可リストです。 Microsoft は、これらの信頼できるメール ソースをサブスクリプションからさまざまなサード パーティのリストに送信された形式で識別します。 セーフ リストの使用を有効または無効にできます。セーフ リストの移行元の電子メール サーバーを構成することはできません。 スパム フィルターは、セーフ リスト上の電子メール サーバーからの受信メッセージにスキップされます。

このトピックでは、セキュリティ & コンプライアンス センターまたは PowerShell (Exchange Online にメールボックスを持つ Microsoft 365 組織用の Exchange Online PowerShell;Exchange Online メールボックスを使用している組織用のスタンドアロン EOP PowerShell) を構成する方法について説明します。 EOP で接続フィルターを使用する方法が組織の全体的なスパム対策設定に含まれますのかについては、「スパム対策保護 [」を参照してください](anti-spam-protection.md)。

> [!NOTE]
> IP 許可一覧、セーフ リスト、IP 禁止一覧は、組織内で電子メールを許可またはブロックする全体的な戦略の一部です。 詳細については、「差出人セー[フ リストを作成する」および「ブロック](create-safe-sender-lists-in-office-365.md)[する差出人リストの作成」を参照してください](create-block-sender-lists-in-office-365.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - 既定の接続フィルター ポリシーを変更するには、次のいずれかの役割グループのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - 既定の接続フィルター ポリシーへの読み取り専用アクセスを行う場合は、次の役割グループのいずれかのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

- 許可またはブロックする電子メール サーバーの送信元 IP アドレス (送信者) を見つけるには、メッセージ ヘッダー内の接続 IP **(CIP)** ヘッダー フィールドを確認します。 さまざまなメール クライアントでメッセージ ヘッダーを表示するには [、「Outlook でインターネット メッセージ ヘッダーを表示する」を参照してください](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。

- IP 許可一覧は IP 禁止一覧より優先されます (両方の一覧のアドレスはブロックされません)。

- IP 許可一覧と IP 禁止一覧は、最大 1,273 個のエントリをサポートします。エントリは、単一の IP アドレス、IP アドレス範囲、またはクラスレス ドメイン間ルーティング (CIDR) IP です。

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>セキュリティ コンプライアンス センターを&、既定の接続フィルター ポリシーを変更する

1. セキュリティ コンプライアンス センター&、脅威管理**ポリシーの** \> **Policy** \> **スパム対策に移動します**。

2. [スパム対策 **の設定] ページで、[** 展開] アイコン **をクリックし、[ポリシーの** 編集] ![ を ](../../media/scc-expand-icon.png) クリックして、[接続フィルター ポリシー] を **展開します**。

3. 表示される **既定** のポップアップで、次のいずれかの設定を構成します。

   - **Description**: 説明テキストを入力します (省略可能)。

   - **IP 許可一覧**: [編集] **をクリックします**。 表示される **IP 許可一覧** のポップアップで、次の構文を使用してアドレスまたはアドレス **範囲ボックスに** IPV4 アドレスを入力します。

     - 単一の IP: 例: 192.168.1.1。

     - IP 範囲: 例: 192.168.0.1 から 192.168.0.254。

     - CIDR IP:例: 192.168.0.1/25。 有効なネットワーク マスク値は /24 ~ /32 です。 CIDR IP マスク値 /1 ~ /23 のスパム フィルター処理をスキップするには、このトピックで後述する使用可能な範囲外の CIDR IP に対する [[Skip spam filtering] (CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) のスパム フィルターをスキップする) を参照してください。

     IP アドレスまたはアドレス範囲を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。 エントリを削除するには、[許可する IP アドレス] のエントリ **を選び** 、[削除] **をクリック** ![ します ](../../media/scc-remove-icon.png) 。 完了したら、**[保存]** をクリックします。

   - **IP 禁止一覧**: [編集] **をクリックします**。 表示される**IP 禁止一**覧のポップアップで、IP 許可一覧の設定で説明したように、アドレス**Address or address range**またはアドレス範囲ボックスに単一の IP、IP アドレス範囲、または CIDR **IP を入力**します。

     IP アドレスまたはアドレス範囲を追加するには、[追加] **アイコンを** ![ クリックします ](../../media/ITPro-EAC-AddIcon.png) 。 エントリを削除するには、[ブロックする IP アドレス] **内のエントリを選び** 、[削除] **をクリック** ![ します ](../../media/scc-remove-icon.png) 。 完了したら、**[保存]** をクリックします。

   - **セーフ リストを有効**にする: セーフ リストの使用を有効または無効にして、スパム フィルター処理をスキップする既知の適切な送信者を識別します。

4. 完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>セキュリティ コンプライアンス センター&を使用して、既定の接続フィルター ポリシーを表示する

1. セキュリティ コンプライアンス センター&、脅威管理**ポリシーの** \> **Policy** \> **スパム対策に移動します**。

2. [スパム **対策の設定] ページで** 、[接続フィルター ポリシー] という名前の既定のポリシーの横の **ドロップダウンをクリックします**。

3. ポリシー設定がドロップダウンに表示され、そのテキストが表示されます。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して既定の接続フィルター ポリシーを変更する

次の構文を使用してください。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**注**:

- 有効な IP アドレスまたはアドレスの範囲の値は次のとおりです。

  - 単一の IP: 例: 192.168.1.1。

  - IP 範囲: 例: 192.168.0.1 から 192.168.0.254。

  - CIDR IP:例: 192.168.0.1/25。 有効なネットワーク マスク値は /24 ~ /32 です。

- 指定 *した値で* 既存のエントリを上書きするには、次の構文を使用します `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。

- 他 *の既存のエントリに* 影響を及ぼせずに IP アドレスまたはアドレス範囲を追加または削除するには、次の構文を使用します `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。

- IP 許可一覧または IP 禁止一覧を空にするには、値を使用します `$null` 。

この例では、IP 許可一覧と IP 禁止一覧を指定された IP アドレスおよびアドレス範囲で構成します。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

この例では、指定した IP アドレスおよびアドレス範囲を IP 許可一覧から追加および削除します。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

構文およびパラメーターの詳細については [、「Set-HostedConnectionFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

既定の接続フィルター ポリシーが正常に変更されたことを確認するには、次のいずれかの手順を実行します。

- セキュリティ/コンプライアンス &で、[ **脅威**管理 \> **ポリシー** \> **のスパム対策]** に \> 移動し、接続フィルター **ポリシーの横にあるドロップ ダウンダウンをクリックし (常にオン)、** 設定を確認します。

- Exchange Online PowerShell またはスタンドアロン EOP PowerShell で、次のコマンドを実行して設定を確認します。

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- IP 許可一覧のエントリからテスト メッセージを送信します。

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 許可一覧の追加の考慮事項

次のセクションでは、IP 許可一覧を構成する際に知っておく必要があるその他の項目を示します。

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>使用可能な範囲外の CIDR IP アドレスに対するスパム フィルターをスキップする

前述したように、IP 許可一覧で使用できるのは、ネットワーク マスク /24 ~ /32 の CIDR IP のみです。 送信元の電子メール サーバーから /23 範囲のソース 電子メール サーバーからのメッセージに対するスパム フィルターをスキップするには、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を使用する必要があります。 ただし、可能な場合には、可能な場合には行わないことをお勧めします。なお、/1 ~ 23 CIDR の IP 範囲内の IP アドレスが Microsoft 独自の信頼できる禁止一覧またはサード パーティ製の任意のブロック リストに表示される場合にメッセージはブロックされるからです。

潜在的な問題を完全に認識しているため、次の設定を使用してメール フロー ルールを作成し、これらの IP アドレスからのメッセージがスパム フィルター処理をスキップするようにすることができます。

- ルールの条件:送信者 IP**アドレスがこれらの範囲**のいずれかまたは完全に一 \> **The sender** \> **致**する \> 場合に、このルールを適用します (/1 ~ /23 ネットワーク マスクで CIDR IP を入力します)。

- ルールの処理: **メッセージ プロパティを変更** \> **し、SCL (Spam Confidence Level)** でスパム \> **フィルターをバイパスします**。

ルールを監査したり、ルールをテストしたり、一定期間にルールをアクティブにしたり、その他の選択項目を指定することができます。 ルールを施行する前に一定期間ルールをテストすることをお勧めします。 詳細については [、「Exchange Online のメール フロー ルールの管理」を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>同じソースから選択的なメール ドメインに対するスパム フィルターをスキップする

通常、IP アドレスまたはアドレス範囲を IP 許可一覧に追加すると、そのメール ソースからのすべての受信メッセージを信頼できます。 ただし、そのソースが複数のドメインから電子メールを送信し、その一部のドメインについてはスパム フィルターをスキップしたい場合があります。その他のドメインについてはスキップしたい場合はどうでしょうか。 IP 許可一覧だけを使用してこの処理を行えることはできますが、IP 許可一覧をメール フロー ルールと組み合わせて使用することができます。

たとえば、送信元電子メール サーバー 192.168.1.25 は contoso.com、fabrikam.com、および tailspintoys.com のドメインから電子メールを送信しますが、fabrikam.com の送信者からのメッセージに対するスパム フィルターをスキップする必要がある場合があります。 これを行うには、次の手順を使用します。

1. IP 許可一覧に 192.168.1.25 を追加します。

2. 次の設定 (最低でも) でメール フロー ルールを構成します:

   - ルールの条件:送信者 IP**アドレスがこのいずれかの**範囲に存在する場合、 \> **The sender** \> **IP address is in any of these ranges or exactly matches**または 192.168.1.25 (前の手順で IP 許可一覧に追加したのと同じ IP アドレスまたはアドレス範囲) に一致する \> 場合に、このルールを適用します。

   - ルールの処理: **メッセージ プロパティを変更** \> **し、SCL (Spam Confidence Level) 0 を設定** \> **します**。

   - ルール例外: **送信者** \> **ドメインがドメインfabrikam.com** \> ドメインが無効である (スパム フィルタリングをスキップするドメインのみ)。

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>IP 許可一覧のソースからのメッセージがフィルター処理を実行するシナリオ

IP 許可一覧内のメール サーバーからのメッセージは、引き続き次のシナリオでスパム フィルター処理の対象になります。

- IP 許可一覧の IP アドレスは、オンプレミス、Microsoft 365 の任意のテナントの*any*IP ベースの受信コネクタ (このテナント A と呼**びます)、** およびメッセージを検出する前の EOP サーバーとも Microsoft データセンターの同じ*Active* Directory フォレスト内に存在するようになります。 このシナリオでは **、IPV:CAL** *が*[(メッセージ](anti-spam-message-headers.md)のスパム フィルター処理をバイパスしたことを示す) メッセージのスパム対策メッセージ ヘッダーに追加されますが、それでもメッセージはスパム フィルター処理の対象になります。

- IP 許可一覧を含むテナントと、最初にメッセージを検出した EOP サーバーは、両方とも Microsoft *データセンター* の異なる Active Directory フォレストに存在する可能性があります。 このシナリオでは **、IPV:CAL** *がメッセージ* ヘッダーに追加されていないため、引き続きメッセージはスパム フィルター処理の対象になります。

これらのシナリオのいずれかに当てはなけた場合、以下の設定を満たすメール フロー ルールを作成して、問題がある IP アドレスからのメッセージがスパム フィルター処理をスキップするようにすることができます。

- ルールの条件:送信者 IP**アドレスがこのいずれかの**範囲に存在する場合、または IP アドレスまたはアドレスと完全 \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> に一致する場合に、このルールを適用します。

- ルールの処理: **メッセージ プロパティを変更** \> **し、SCL (Spam Confidence Level)** でスパム \> **フィルターをバイパスします**。

## <a name="new-to-microsoft-365"></a>Microsoft 365 を使用するのは?

|<!-- a -->|
|---|
|![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **to Microsoft 365 の小さいアイコン** LinkedIn Learning が提供する管理者および **IT**プロダッシー向けの無料のビデオ コースをご覧ください。|
|
