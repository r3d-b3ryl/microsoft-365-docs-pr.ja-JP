---
title: 既定の接続フィルターポリシーを構成する
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
description: 管理者は、Exchange Online Protection (EOP) で、電子メールサーバーからのメールを許可またはブロックするように接続フィルターを構成する方法について説明します。
ms.openlocfilehash: d69ec30c9d6d812bf3bbcc6dc5b6df332d9dd0b5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203373"
---
# <a name="configure-connection-filtering"></a>接続フィルターの構成

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online または exchange online メールボックスを持たないスタンドアロンの Exchange Online Protection (EOP) 顧客のメールボックスを使用している Microsoft 365 顧客の場合は、EOP (特に既定の接続フィルターポリシー) で接続フィルターを使用して、適切なまたは不良なソース電子メールサーバーを IP アドレスで識別します。 既定の接続フィルター ポリシーの主な構成要素は次のとおりです。

- **Ip 許可一覧**: ip アドレスまたは ip アドレス範囲で指定した送信元電子メールサーバーからのすべての受信メッセージに対してスパムフィルター処理をスキップします。 このようなソースからのメッセージにスパムフィルター処理が依然として発生する可能性があるシナリオについては、このトピックで後述する「 [IP 許可一覧のソースからのメッセージのフィルター処理](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 」セクションを参照してください。 IP 許可一覧が安全な送信者戦略全体にどのように適合するかの詳細については、「 [EOP での安全な送信者リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。

- **Ip 禁止一覧**: ip アドレスまたは ip アドレス範囲で指定した送信元電子メールサーバーからのすべての受信メッセージをブロックします。 受信メッセージは拒否され、スパムとしてマークされないため、追加のフィルター処理は行われません。 IP 禁止一覧がブロックされる送信者の全体的な戦略にどのように適合するかの詳細については、「 [Create Block sender lists IN EOP](create-block-sender-lists-in-office-365.md)」を参照してください。

- **セーフリスト**: *セーフリスト* は、お客様の構成を必要としない、Microsoft データセンターの動的な許可一覧です。 Microsoft では、これらの信頼できる電子メールソースを、さまざまなサードパーティリストに対するサブスクリプションから識別しています。 セーフリストの使用を有効または無効にします。送信元の電子メールサーバーをセーフリストで構成することはできません。 セーフリスト上の電子メールサーバーからの受信メッセージに対して、スパムフィルター処理がスキップされます。

このトピックでは、セキュリティ & コンプライアンスセンターまたは PowerShell (exchange online のメールボックスを使用する Microsoft 365 組織の場合は exchange online PowerShell、exchange online メールボックスがない組織の場合は、スタンドアロン EOP PowerShell) で既定の接続フィルターポリシーを構成する方法について説明します。 EOP での接続フィルターの使用方法については、「スパム対策 [保護](anti-spam-protection.md)を参照する」を参照してください。

> [!NOTE]
> IP 許可一覧、セーフリスト、および IP 禁止一覧は、組織内の電子メールを許可またはブロックするための全体的な戦略の一部です。 詳細については、「 [差出人セーフリストを作成する](create-safe-sender-lists-in-office-365.md) 」および「 [ブロックする送信者リストを作成する](create-block-sender-lists-in-office-365.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- このトピックの手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。

  - 既定の接続フィルターポリシーを変更するには、次のいずれかの役割グループのメンバーである必要があります。

    - **組織の管理**または[セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ管理者**。
    - **組織の管理**または [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**検疫管理**。

  - 既定の接続フィルターポリシーに対する読み取り専用アクセスでは、次のいずれかの役割グループのメンバーである必要があります。

    - [セキュリティ/コンプライアンス センター](permissions-in-the-security-and-compliance-center.md)の**セキュリティ閲覧者**。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) の**表示限定の組織管理**。

- 許可またはブロックする電子メールサーバー (送信者) の送信元 IP アドレスを確認するには、メッセージヘッダーの [接続 IP (**CIP**)] ヘッダーフィールドを確認します。 さまざまな電子メールクライアントのメッセージヘッダーを表示するには、「 [Outlook でインターネットメッセージヘッダーを表示](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)する」を参照してください。

- IP 許可一覧は、IP 禁止一覧より優先されます (両方のリストのアドレスがブロックされることはありません)。

- IP 許可一覧と IP 禁止一覧には、最大で1273エントリがサポートされています。これは、1つの IP アドレス、IP アドレスの範囲、またはクラスレスドメイン間ルーティング (CIDR) IP です。

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>セキュリティ & コンプライアンスセンターを使用して既定の接続フィルターポリシーを変更する

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理**ポリシーのスパム対策] に移動し \> **Policy** \> **Anti-Spam**ます。

2. [ **スパム対策設定** ] ページで、[展開] アイコンをクリックして [ **接続フィルターポリシー** ] を展開し、 ![ ](../../media/scc-expand-icon.png) [ **ポリシーの編集**] をクリックします。

3. 表示される **既定** のポップアップで、次のいずれかの設定を構成します。

   - **説明**: オプションで説明テキストを入力します。

   - **IP 許可一覧**: [ **編集**] をクリックします。 表示された **IP 許可一覧** のポップアップで、次の構文を使用して、[ **アドレスまたはアドレスの範囲** ] ボックスに IPV4 アドレスを入力します。

     - 単一の IP: たとえば、192.168.1.1。

     - IP 範囲: たとえば、192.168.0.1-192.168.0.254。

     - CIDR IP: たとえば、192.168.0.1/25。 有効なネットワークマスク値は、/24 ~ 32 です。 CIDR IP マスク値/1 から/23 へのスパムフィルター処理をスキップするには、このトピックで後述する「 [使用可能な範囲外の CIDR ip のスパムフィルタリングをスキップ](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) する」を参照してください。

     IP アドレスまたはアドレスの範囲を追加するには、[追加] アイコン **をクリックし** ![ ](../../media/ITPro-EAC-AddIcon.png) ます。 エントリを削除するには、[ **許可された IP アドレス** ] でエントリを選択し、 **[削除] をクリックし** ![ ](../../media/scc-remove-icon.png) ます。 完了したら、**[保存]** をクリックします。

   - **IP 禁止一覧**: [ **編集**] をクリックします。 表示される**Ip 禁止一覧**のポップアップで、Ip**許可一覧**の設定で前述したように、[**アドレスまたはアドレスの範囲**] ボックスに1つの ip、IP 範囲、または CIDR IP を入力します。

     IP アドレスまたはアドレスの範囲を追加するには、[追加] アイコン **をクリックし** ![ ](../../media/ITPro-EAC-AddIcon.png) ます。 エントリを削除するには、[ **ブロックする IP アドレス** ] のエントリを選択し、 **[削除] をクリックし** ![ ](../../media/scc-remove-icon.png) ます。 完了したら、**[保存]** をクリックします。

   - **セーフ**リストを有効にする: セーフリストの使用を有効または無効にして、スパムフィルターをスキップする既知の良好な送信者を特定します。

4. 完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>セキュリティ & コンプライアンスセンターを使用して既定の接続フィルターポリシーを表示する

1. [セキュリティ & コンプライアンスセンター] で、[**脅威管理**ポリシーのスパム対策] に移動し \> **Policy** \> **Anti-Spam**ます。

2. [ **スパム対策設定** ] ページで、[ **接続フィルターポリシー**] という名前の既定のポリシーの横にあるドロップダウンをクリックします。

3. ポリシー設定が、表示されるドロップダウンに表示されます。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Exchange Online PowerShell またはスタンドアロンの EOP PowerShell を使用して既定の接続フィルターポリシーを変更する

次の構文を使用してください。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**注**:

- 有効な IP アドレスまたはアドレス範囲の値は次のとおりです。

  - 単一の IP: たとえば、192.168.1.1。

  - IP 範囲: たとえば、192.168.0.1-192.168.0.254。

  - CIDR IP: たとえば、192.168.0.1/25。 有効なネットワークマスク値は、/24 ~ 32 です。

- 既存のエントリを指定した値で *上書き* するには、次の構文を使用し `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` ます。

- 他の既存のエントリに影響を及ぼさずに、IP アドレスまたはアドレス範囲を *追加または削除* するには、次の構文を使用し `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` ます。

- IP 許可一覧または IP 禁止一覧を空にするには、値を使用し `$null` ます。

この例では、指定した IP アドレスとアドレス範囲を使用して ip 許可一覧と IP 禁止一覧を構成します。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

この例では、指定された IP アドレスとアドレス範囲を IP 許可一覧から追加または削除します。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

構文およびパラメーターの詳細については、「 [remove-hostedconnectionfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

既定の接続フィルターポリシーが正常に変更されたことを確認するには、次のいずれかの手順を実行します。

- [セキュリティ & コンプライアンスセンター] で、[**脅威管理**ポリシーのスパム対策] に移動し \> **Policy** \> **Anti-Spam** \> て、[**接続フィルターポリシー (always ON**)] の横にあるドロップダウンをクリックし、設定を確認します。

- Exchange Online PowerShell またはスタンドアロンの EOP PowerShell で、次のコマンドを実行し、設定を確認します。

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- IP 許可一覧のエントリからテストメッセージを送信します。

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 許可一覧に関するその他の考慮事項

次のセクションでは、IP 許可一覧を構成する際に知っておく必要があるその他の項目について説明します。

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>使用可能な範囲外の CIDR IP のスパムフィルタリングをスキップする

このトピックの前半で説明したように、IP 許可一覧では、ネットワークマスク/24 ~ 32 の CIDR IP のみを使用できます。 /1 から/23 の範囲のソース電子メールサーバーからのメッセージに対するスパムフィルター処理をスキップするには、Exchange メールフロールール (トランスポートルールとも呼ばれる) を使用する必要があります。 ただし、Microsoft の専用またはサードパーティのブロックリストのいずれかに、[/1 ~ 23 CIDR IP] 範囲の IP アドレスが表示される場合は、メッセージがブロックされるため、この操作は可能な限り行うことをお勧めします。

潜在的な問題について十分に理解できたので、以下の設定を使用してメールフロールールを作成し、これらの IP アドレスからのメッセージがスパムフィルタリングをスキップするようにすることができます。

- ルールの条件**Apply this rule if** : \> **送信者**の \> **ip アドレスがこれらのいずれかの範囲内にある場合、または完全に一致する**場合は、このルールを適用 \> します (/1 ~ 23 のネットワークマスクで CIDR ip を入力します)。

- ルールの処理: **メッセージのプロパティを変更する** \> **スパム信頼レベル (SCL) を設定**する \> **スパムフィルターをバイパス**する。

ルールを監査したり、ルールをテストしたり、特定の期間にルールをアクティブ化したり、その他の選択を行ったりすることができます。 ルールを施行する前に一定期間ルールをテストすることをお勧めします。 詳細については、「 [Exchange Online でメールフロールールを管理](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)する」を参照してください。

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>同じソースから選択したメールドメインでスパムフィルター処理をスキップする

通常、ip アドレスまたはアドレス範囲を IP 許可一覧に追加すると、その電子メールソースからのすべての受信メッセージが信頼できるようになります。 しかし、送信元が複数のドメインからメールを送信している場合に、それらのドメインの一部に対してスパムフィルター処理をスキップする必要がある場合はどうすればよいでしょうか。 IP 許可一覧のみを使用してこれを行うことはできませんが、IP 許可一覧はメールフロールールと組み合わせて使用できます。

たとえば、ソースメールサーバー192.168.1.25 は、ドメイン contoso.com、fabrikam.com、および tailspintoys.com から電子メールを送信しますが、fabrikam.com の送信者からのメッセージに対してのみスパムフィルターをスキップしたいとします。 これを行うには、次の手順を使用します。

1. 192.168.1.25 を IP 許可一覧に追加します。

2. 少なくとも次の設定を使用してメールフロールールを構成します。

   - ルールの条件**Apply this rule if** : \> **送信者**の \> **IP アドレスがこれらのいずれかの範囲内にある場合、または** \> 192.168.1.25 (前の手順で ip 許可一覧に追加したものと同じ ip アドレスまたはアドレスの範囲) に正確に一致する場合は、このルールを適用します。

   - ルールの処理: **メッセージのプロパティを変更する** \> **スパム信頼レベル (SCL)** \> **0**を設定します。

   - ルールの例外: **送信者** \> **ドメインは** \> fabrikam.com です (スパムフィルターをスキップするドメインのみ)。

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>IP 許可一覧のソースからのメッセージが引き続きフィルター処理されるシナリオ

IP 許可一覧内の電子メールサーバーからのメッセージは、次のシナリオでは依然としてスパムフィルター処理の対象となります。

- IP 許可一覧の ip アドレスは、Microsoft 365 の *任意* のテナントのオンプレミスの ip ベースの受信コネクタにも構成されています (このテナントを呼び出すことができます) **。また、** 最初にメッセージが検出された EOP サーバーが、microsoft データセンター内の *同じ* Active Directory フォレストに存在することになります。 このシナリオでは、 **Ipv: CAL** *が* メッセージの [スパム対策メッセージヘッダー](anti-spam-message-headers.md) に追加されます (メッセージがスパムフィルタリングをバイパスしていることを示します)。ただし、メッセージはスパムフィルター処理の対象となります。

- IP 許可一覧を含むテナントと、最初にメッセージを検出した EOP サーバーの両方が、Microsoft データセンター内の *異なる* Active Directory フォレストに存在する。 このシナリオでは、 **Ipv: CAL** *は* メッセージヘッダーに追加されないため、メッセージはスパムフィルター処理の対象となります。

これらのシナリオのいずれかが発生した場合は、次の設定を使用してメールフロールールを作成することができます (最低限)。これにより、問題のある IP アドレスからのメッセージがスパムフィルター処理をスキップすることを確認できます。

- ルールの条件**Apply this rule if** : \> **送信者の** \> **IP アドレスがこれらの範囲内にある場合、または完全に一致する**場合は \> (IP アドレスまたはアドレス)、このルールを適用します。

- ルールの処理: **メッセージのプロパティを変更する** \> **スパム信頼レベル (SCL) を設定**する \> **スパムフィルターをバイパス**する。

## <a name="new-to-microsoft-365"></a>Microsoft 365 の新機能

|<!-- a -->|
|---|
|![LinkedIn Learning の短いアイコンは、 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365 に新しいものですか?** LinkedIn ラーニングによって提供される **管理者と IT プロフェッショナル**向けの無料のビデオコースを見つけることができます。|
|
