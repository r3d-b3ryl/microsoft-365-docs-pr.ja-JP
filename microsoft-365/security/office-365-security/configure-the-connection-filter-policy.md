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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で接続フィルターを構成して、電子メール サーバーからのメールを許可またはブロックする方法について説明します。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 1e82df7ac66b11b323d88c00d29a89d7c9d3e237
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483104"
---
# <a name="configure-connection-filtering"></a>接続フィルターを構成する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineのメールボックスを持つ Microsoft 365 のお客様、またはExchange Onlineメールボックスのないスタンドアロン Exchange Online Protection (EOP) のお客様の場合は、EOP (具体的には既定の接続フィルター ポリシー) で接続フィルター処理を使用して、IP アドレスによって適切または不適切なソース 電子メール サーバーを識別します。 既定の接続フィルター ポリシーの主な構成要素は次のとおりです。

- **IP 許可一覧: IP** アドレスまたは IP アドレス範囲で指定した送信元電子メール サーバーからのすべての受信メッセージのスパム フィルター処理をスキップします。 これらのソースからのメッセージでスパム フィルター処理が引き続き発生する可能性があるシナリオについては、この記事の後半の「 [IP 許可リストのソースからのメッセージが引き続きフィルター処理されるシナリオ](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 」を参照してください。 IP 許可リストが全体の安全な送信者戦略にどのように適合するかの詳細については、「 [EOP での差出人セーフ リストの作成](create-safe-sender-lists-in-office-365.md)」を参照してください。

- **IP 禁止リスト: IP** アドレスまたは IP アドレス範囲で指定した送信元電子メール サーバーからの受信メッセージをすべてブロックします。 受信メッセージは拒否され、スパムとしてマークされず、追加のフィルター処理は行われません。 IP ブロック リストがブロックされた送信者の全体的な戦略にどのように適合するかの詳細については、 [EOP でのブロック送信者リストの作成に](create-block-sender-lists-in-office-365.md)関するページを参照してください。

- **セーフ リスト**: *セーフ リスト* は、お客様の構成を必要としない、Microsoft データセンター内の動的な許可リストです。 Microsoft は、これらの信頼できる電子メール ソースをサブスクリプションからさまざまなサード パーティのリストに識別します。 セーフ リストの使用を有効または無効にします。セーフ リストにソース電子メール サーバーを構成することはできません。 スパム フィルターは、セーフ リスト上の電子メール サーバーからの受信メッセージではスキップされます。

この記事では、Microsoft 365 Microsoft 365 Defender ポータルまたは PowerShell で既定の接続フィルター ポリシーを構成する方法について説明します (Exchange Onlineにメールボックスを含む Microsoft 365 組織の PowerShell をExchange Onlineし、スタンドアロンの EOP PowerShell を使用しない組織向けExchange Online メールボックス)。 EOP が組織の全体的なスパム対策設定の一部である接続フィルターを使用する方法の詳細については、 [スパム対策の保護](anti-spam-protection.md)に関するページを参照してください。

> [!NOTE]
> IP 許可リスト、セーフ リスト、および IP ブロック リストは、組織内のメールを許可またはブロックするための全体的な戦略の 1 つです。 詳細については、「 [差出人セーフ リストの作成](create-safe-sender-lists-in-office-365.md) 」と「 [ブロックされた送信者リストの作成](create-block-sender-lists-in-office-365.md)」を参照してください。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - 既定の接続フィルター ポリシーを変更するには、 **組織の管理** または **セキュリティ管理者** の役割グループのメンバーである必要があります。
  - 既定の接続フィルター ポリシーへの読み取り専用アクセスの場合は、 **グローバル 閲覧者** または **セキュリティ 閲覧者** ロール グループのメンバーである必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 許可またはブロックする電子メール サーバー (送信者) の送信元 IP アドレスを確認するには、メッセージ ヘッダーの接続 IP (**CIP**) ヘッダー フィールドを確認します。 さまざまな電子メール クライアントでメッセージ ヘッダーを表示するには、「 [Outlook でインターネット メッセージ ヘッダーを表示する](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)」を参照してください。

- IP 許可リストは、IP ブロック リストよりも優先されます (両方のリストのアドレスはブロックされません)。

- IP 許可リストと IP ブロック リストは、それぞれ最大 1273 エントリをサポートします。エントリは 1 つの IP アドレス、IP アドレス範囲、またはクラスレス InterDomain ルーティング (CIDR) IP です。

## <a name="use-the-microsoft-365-defender-portal-to-modify-the-default-connection-filter-policy"></a>Microsoft 365 Defender ポータルを使用して既定の接続フィルター ポリシーを変更する

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. [ **スパム対策ポリシー** ] ページで、ポリシーの名前をクリックして、一覧から **[接続フィルター ポリシー ] (既定値)** を選択します。

3. 表示されるポリシーの詳細ポップアップで、次のいずれかの設定を構成します。

   - **[説明** ] セクション: **[名前と説明の編集]** をクリックします。 表示される **[名前と説明の編集]** ポップアップで、[ **説明** ] ボックスに省略可能な説明テキストを入力します。

     完了したら、**[保存]** をクリックします。

   - **[接続フィルター] セクション**: [ **接続フィルター ポリシーの編集]** をクリックします。 表示されるポップアップで、次の設定を構成します。

     - **次の IP アドレスまたはアドレス範囲からのメッセージを常に許可** します。これは IP 許可リストです。 ボックス内をクリックして値を入力し、Enter キーを押すか、ボックスの下に表示される完全な値を選択します。 有効な値は次のとおりです。
       - 単一 IP: たとえば、192.168.1.1 です。
       - IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。
       - CIDR IP: たとえば、192.168.0.1/25 です。 有効なサブネット マスクの値は、/24 ~ /32 です。 /1 から /23 のスパム フィルター処理をスキップするには、この記事の後半の「 [使用可能な範囲外の CIDR IP のスパム フィルターをスキップする](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 」セクションを参照してください。

       必要な回数だけこの手順を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

     IP アドレスまたはアドレス範囲を追加するには、ボックスをクリックして「アイコンの **追加**![](../../media/ITPro-EAC-AddIcon.png)」と入力します。 エントリを削除するには、[ **許可された IP アドレス** ] でエントリを選択し、[ **削除]** ![をクリックします](../../media/scc-remove-icon.png)。 完了したら、**[保存]** をクリックします。

   - **次の IP アドレスまたはアドレス範囲からのメッセージを常にブロック** します。これは IP ブロック リストです。 「次の IP アドレスまたはアドレス範囲からのメッセージを常に許可する」の設定で説明したように、ボックスに **単一の IP、IP 範囲、または** CIDR IP を入力します。

   - **セーフ リストを有効にする**: セーフ リストの使用を有効または無効にして、スパム フィルター処理をスキップする既知の適切な送信者を特定します。 セーフ リストを使用するには、チェック ボックスをオンにします。

   完了したら、**[保存]** をクリックします。

4. ポリシーの詳細ポップアップに戻り、**[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-the-default-connection-filter-policy"></a>Microsoft 365 Defender ポータルを使用して、既定の接続フィルター ポリシーを表示する

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. [ **スパム対策ポリシー** ] ページで、ポリシーの一覧に次のプロパティが表示されます。

   - **名前**: この値は、 **既定の接続フィルター ポリシーの接続フィルター ポリシー (既定値)** です。
   - **状態**: この値は、既定の接続フィルター ポリシーでは **常にオン** です。
   - **優先度**: この値は、既定の接続フィルター ポリシーの **[最低]** です。
   - **型**: この値は、既定の接続フィルター ポリシーでは空白です。

3. 既定の接続フィルター ポリシーを選択すると、ポリシー設定がポップアップに表示されます。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>PowerShell またはスタンドアロン EOP PowerShell Exchange Onlineを使用して、既定の接続フィルター ポリシーを変更する

次の構文を使用してください。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**注**:

- 有効な IP アドレスまたはアドレス範囲の値は次のとおりです。
  - 単一 IP: たとえば、192.168.1.1 です。
  - IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。
  - CIDR IP: たとえば、192.168.0.1/25 です。 有効なネットワーク マスク値は 、/24 ~ /32 です。
- 指定した値で既存のエントリを *上書き* するには、次の構文を使用します `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN`。
- 他の既存のエントリに影響を与えずに IP アドレスまたはアドレス範囲を *追加または削除* するには、次の構文を使用します `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}`。
- IP 許可リストまたは IP ブロック リストを空にするには、値 `$null`を使用します。

この例では、指定した IP アドレスとアドレス範囲を使用して、IP 許可リストと IP ブロック リストを構成します。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

この例では、指定した IP アドレスとアドレス範囲を IP 許可リストに追加および削除します。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

構文とパラメーターの詳細については、「 [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy)」を参照してください。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

既定の接続フィルター ポリシーが正常に変更されたことを確認するには、次のいずれかの手順を実行します。

- Microsoft 365 Defender ポータルの [**スパム対策**] ページで<https://security.microsoft.com/antispam>、ポリシーの名前をクリックして一覧から **[接続フィルター ポリシー (既定値)]** を選択し、設定を確認します。

- Exchange Online PowerShell またはスタンドアロン EOP PowerShell で、次のコマンドを実行し、設定を確認します。

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- IP 許可リストのエントリからテスト メッセージを送信します。

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 許可リストに関するその他の考慮事項

次のセクションでは、IP 許可リストを構成するときに知っておくべきことを示します。

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>使用可能な範囲外の CIDR IP のスパム フィルター処理をスキップする

この記事で前述したように、IP 許可リストのネットワーク マスク /24 ~ /32 でのみ CIDR IP を使用できます。 /1 ~ /23 の範囲の送信元メール サーバーからのメッセージに対するスパム フィルターをスキップするには、Exchange メール フロー ルール (トランスポート ルールとも呼ばれます) を使用する必要があります。 ただし、/1 ~ /23 CIDR IP 範囲の IP アドレスが Microsoft 独自またはサードパーティ製のブロック リストに表示される場合、メッセージはブロックされるため、可能な限りこれを行わないようにすることをお勧めします。

潜在的な問題を十分に認識したので、(少なくとも) 次の設定でメール フロー ルールを作成し、これらの IP アドレスからのメッセージがスパム フィルター処理をスキップするようにすることができます。

- ルールの条件: **送信者** \> **の IP アドレスがこれらの範囲内にある場合、または完全に一致** \> する場合\>は **、この規則を適用** します (CIDR IP を /1 ~ /23 のネットワーク マスクで入力します)。
- ルール アクション: **メッセージプロパティ**\>を変更 **する スパム信頼レベル (SCL)** \> **スパム フィルターをバイパスする** を設定します。

ルールの監査、ルールのテスト、特定の期間中のルールのアクティブ化、その他の選択を行うことができます。 ルールを施行する前に一定期間ルールをテストすることをお勧めします。 詳細については、「[Exchange Onlineでのメール フロー ルールの管理](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)」を参照してください。

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>同じソースからの選択的な電子メール ドメインでのスパム フィルター処理をスキップする

通常、IP アドレスまたはアドレス範囲を IP 許可リストに追加すると、その電子メール ソースからのすべての受信メッセージが信頼されます。 しかし、そのソースが複数のドメインから電子メールを送信し、それらのドメインの一部に対してスパム フィルター処理をスキップしたいが、他のドメインには送信しない場合はどうでしょうか。 IP 許可リストだけを使用してこれを行うことはできませんが、IP 許可リストをメール フロー ルールと組み合わせて使用できます。

たとえば、送信元電子メール サーバー 192.168.1.25 は、ドメイン contoso.com、fabrikam.com、tailspintoys.com から電子メールを送信しますが、fabrikam.com の送信者からのメッセージのスパム フィルター処理のみをスキップします。 これを行うには、次の手順を実行します。

1. IP 許可リストに 192.168.1.25 を追加します。

2. 次の設定を使用してメール フロー ルールを構成します (少なくとも)。
   - ルール条件: **送信者** \> **の IP アドレスがこれらの範囲内にある場合、または** 192.168.1.25 (前の手順で IP 許可リストに追加したものと同じ IP アドレスまたはアドレス範囲) と完全に一致\>する場合\>は、**この規則を適用** します。
   - ルール アクション: **メッセージプロパティ**\>を変更 **する スパム信頼レベル (SCL)** \> **0** を設定します。
   - ルール例外: **送信者** \> **ドメインは** \> fabrikam.com です (スパム フィルター処理をスキップするドメインまたはドメインのみ)。

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>IP 許可リスト内のソースからのメッセージが引き続きフィルター処理されるシナリオ

IP 許可リスト内の電子メール サーバーからのメッセージは、次のシナリオでは引き続きスパム フィルターの対象となります。

- IP 許可リストの IP アドレスは、Microsoft 365 *内の任意* のテナントのオンプレミスの IP ベースの受信コネクタ (このテナント A を呼び出 **しましょう)、** および最初にメッセージが発生したテナント A と EOP サーバーの両方が、Microsoft データセンター内の *同じ* Active Directory フォレストに存在するように構成されています。 このシナリオでは、メッセージの [スパム対策メッセージ ヘッダー](anti-spam-message-headers.md) (メッセージバイパスされたスパム フィルターを示す) に **IPV:CAL** *が追加されますが*、メッセージは引き続きスパム フィルター処理の対象となります。

- IP 許可一覧を含むテナントと、最初にメッセージが表示される EOP サーバーの両方が、Microsoft データセンター内 *の異なる* Active Directory フォレストに存在する可能性があります。 このシナリオでは、 **IPV:CAL** *は* メッセージ ヘッダーに追加されないため、メッセージはスパム フィルター処理の対象となります。

これらのシナリオのいずれかが発生した場合は、(少なくとも) 次の設定を使用してメール フロー ルールを作成し、問題のある IP アドレスからのメッセージがスパム フィルター処理をスキップするようにすることができます。

- ルールの条件: **送信者** \> **の IP アドレスがこれらの範囲内にある場合、または完全に一致** \> する (IP アドレスまたはアドレス) 場合\>は、**このルールを適用** します。
- ルール アクション: **メッセージプロパティ**\>を変更 **する スパム信頼レベル (SCL)** \> **スパム フィルターをバイパスする** を設定します。

## <a name="new-to-microsoft-365"></a>Microsoft 365 の新機能

****

LinkedIn ラーニングのショート アイコンです。Office 365 を初めてお使いの場合は         、LinkedIn ラーニングによって提供された Office 365 管理者および IT プロフェッショナル向けの無料のビデオコースをご覧ください。 **Microsoft 365 の新機能** LinkedIn Learning によって提供される **、Microsoft 365 管理者と IT 担当者** 向けの無料のビデオ コースをご覧ください。
