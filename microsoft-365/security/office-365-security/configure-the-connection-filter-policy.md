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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理者は、Exchange Online Protection (EOP) で接続フィルターを構成して、電子メール サーバーからの電子メールを許可またはブロックする方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef81d602e1f6da368e9d469bf1deaf0ef2c0a6af
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165753"
---
# <a name="configure-connection-filtering"></a>接続フィルターを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Exchange Online のメールボックスを使用している Microsoft 365 のお客様、または Exchange Online メールボックスを使用しないスタンドアロンの Exchange Online Protection (EOP) のお客様の場合は、EOP の接続フィルター (具体的には既定の接続フィルター ポリシー) を使用して、送信元の電子メール サーバーを IP アドレスで識別します。 既定の接続フィルター ポリシーの主な構成要素は次のとおりです。

- **IP 許可一覧**: IP アドレスまたは IP アドレス範囲で指定した送信元電子メール サーバーからのすべての受信メッセージに対するスパム フィルター処理をスキップします。 これらのソースからのメッセージに対してスパム フィルターが引き続き発生する可能性があるシナリオについては、この記事の後半の [「IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 許可一覧の送信元からのメッセージがフィルター処理されるシナリオ」を参照してください。 IP 許可一覧が全体的な差出人セーフ リスト戦略に適合する方法の詳細については [、「EOP](create-safe-sender-lists-in-office-365.md)で差出人セーフ リストを作成する」を参照してください。

- **IP ブロック リスト**: IP アドレスまたは IP アドレス範囲で指定した送信元電子メール サーバーからの受信メッセージをすべてブロックします。 受信メッセージは拒否され、スパムとしてマークされません。また、追加のフィルター処理は行われません。 IP 受信拒否リストを受信拒否戦略全体に適合する方法の詳細については [、「EOP](create-block-sender-lists-in-office-365.md)で受信拒否リストを作成する」を参照してください。

- **セーフ リスト**: セーフ *リストは* 、Microsoft データセンター内の動的な許可リストで、顧客の構成は必要とされません。 Microsoft は、サブスクリプションからさまざまなサード パーティのリストへの信頼できる電子メール ソースを識別します。 セーフ リストの使用を有効または無効にします。セーフ リストでソース メール サーバーを構成できません。 スパム フィルターは、セーフ リスト上の電子メール サーバーからの受信メッセージではスキップされます。

このトピックでは、セキュリティ & コンプライアンス センターまたは PowerShell で既定の接続フィルター ポリシーを構成する方法について説明します (Exchange Online にメールボックスがある Microsoft 365 組織向け Exchange Online PowerShell、Exchange Online メールボックスのない組織のスタンドアロン EOP PowerShell)。 EOP が接続フィルターを使用する方法の詳細については、組織の全体的なスパム対策設定の一部です。「スパム対策保護 [」を参照してください](anti-spam-protection.md)。

> [!NOTE]
> IP 許可一覧、セーフ リスト、IP ブロック リストは、組織内の電子メールを許可またはブロックする全体的な戦略の 1 部です。 詳細については、「安全な差出人[のリストを作成する」および「](create-safe-sender-lists-in-office-365.md)[受信拒否リストを作成する」を参照してください](create-block-sender-lists-in-office-365.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://protection.office.com/> でセキュリティ/コンプライアンス センターを開きます。 **[スパム対策の設定]** ページに直接移動するには、<https://protection.office.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事に記載の手順を行うには、セキュリティ/コンプライアンス センターのアクセス許可が割り当てられている必要があります。
  - 既定の接続フィルター ポリシーを変更するには、組織の管理役割グループまたはセキュリティ管理者役割グループのメンバー **である** 必要があります。
  - 既定の接続フィルター ポリシーに読み取り専用でアクセスするには、グローバル閲覧者またはセキュリティ閲覧者の役割グループのメンバー **である必要があります**。

  詳細については、「[セキュリティ/コンプライアンス センターのアクセス許可](permissions-in-the-security-and-compliance-center.md)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory の役割にユーザーを追加すると、ユーザーには、セキュリティ/コンプライアンス センター の必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。 詳細については、「[管理者の役割について](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 許可またはブロックする電子メール サーバー (送信者) の送信元 IP アドレスを検索するには、メッセージ ヘッダーの接続 IP **(CIP)** ヘッダー フィールドを確認します。 さまざまな電子メール クライアントでメッセージ ヘッダーを表示するには、「Outlook でインターネット メッセージ ヘッダーを表示する」 [を参照してください](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)。

- IP 許可一覧は IP ブロック リストよりも優先されます (両方のリストのアドレスはブロックされません)。

- IP 許可一覧と IP ブロック リストは、それぞれ最大 1273 エントリをサポートします。エントリは、単一の IP アドレス、IP アドレス範囲、またはクラスレス ドメイン間ルーティング (CIDR) IP です。

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>セキュリティ/コンプライアンス センター&使用して既定の接続フィルター ポリシーを変更する

1. セキュリティ/コンプライアンス センター&、脅威管理 **ポリシー** のスパム対策 \> **に** \> **移動します**。

2. [スパム対策 **の設定]** ページで、[展開] アイコンをクリックして接続フィルター ポリシーを展開し、[ポリシーの編集] ![ ](../../media/scc-expand-icon.png) **をクリックします**。

3. 表示される **既定** のフライアウトで、次の設定を構成します。

   - **説明**: オプションの説明テキストを入力します。

   - **IP 許可一覧**: [編集] **をクリックします**。 表示される **IP 許可一覧** のフライアウトで、次の構文を使用して、[アドレスまたはアドレス範囲] ボックスに IPV4 アドレスを入力します。

     - 単一の IP: たとえば、192.168.1.1。

     - IP 範囲: 例: 192.168.0.1-192.168.0.254。

     - CIDR IP: 例: 192.168.0.1/25。 有効なネットワーク マスク値は 、/24 ~ /32 です。 CIDR IP マスク値 /1 ~ /23 のスパム フィルター処理をスキップするには、この記事の後半の「利用可能な範囲以外の [CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) のスパム フィルター処理をスキップする」を参照してください。

     IP アドレスまたはアドレス範囲を追加するには、[追加] アイコン ![ をクリックします ](../../media/ITPro-EAC-AddIcon.png) 。 エントリを削除するには、[許可された **IP** アドレス] のエントリを選択し、[削除] を **クリック** ![ します ](../../media/scc-remove-icon.png) 。 完了したら、**[保存]** をクリックします。

   - **IP Block List**: Click **Edit**. 表示される **IP ブロック リスト** のフライアウトで、IP 許可一覧の設定で前述したように、[アドレスまたはアドレスの範囲] ボックスに単一の IP、IP 範囲、または CIDR IP を入力します。

     IP アドレスまたはアドレス範囲を追加するには、[追加] アイコン ![ をクリックします ](../../media/ITPro-EAC-AddIcon.png) 。 エントリを削除するには、[ブロックする IP アドレス] のエントリを選択し **、[** 削除] を **クリック** ![ します ](../../media/scc-remove-icon.png) 。 完了したら、**[保存]** をクリックします。

   - **セーフ リストを** 有効にする: セーフ リストの使用を有効または無効にして、スパム フィルタリングをスキップする既知の優れた送信者を特定します。

4. 完了したら、**[保存]** をクリックします。

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>セキュリティ/コンプライアンス センター&使用して既定の接続フィルター ポリシーを表示する

1. セキュリティ/コンプライアンス センター&、脅威管理 **ポリシー** のスパム対策 \> **に** \> **移動します**。

2. [スパム対策 **の設定]** ページで、接続フィルター ポリシーという名前の既定のポリシーの横にあるドロップダウン **をクリックします**。

3. ポリシー設定が開くドロップダウンに表示されます。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>Exchange Online PowerShell またはスタンドアロン EOP PowerShell を使用して既定の接続フィルター ポリシーを変更する

次の構文を使用してください。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**注**:

- 有効な IP アドレスまたはアドレス範囲の値は次のとおりです。

  - 単一の IP: たとえば、192.168.1.1。

  - IP 範囲: 例: 192.168.0.1-192.168.0.254。

  - CIDR IP: 例: 192.168.0.1/25。 有効なネットワーク マスク値は 、/24 ~ /32 です。

- 指定 *した* 値で既存のエントリを上書きするには、次の構文を使用します `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。

- 他 *の既存のエントリに* 影響を及ぼさずに IP アドレスまたはアドレス範囲を追加または削除するには、次の構文を使用します `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。

- IP 許可一覧または IP ブロック 一覧を空にする場合は、値を使用します `$null` 。

この例では、指定された IP アドレスとアドレス範囲を持つ IP 許可一覧と IP ブロック 一覧を構成します。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

この例では、指定した IP アドレスとアドレス範囲を IP 許可一覧に追加および削除します。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

構文およびパラメーターの詳細については [、「Set-HostedConnectionFilterPolicy」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)。

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

既定の接続フィルター ポリシーが正常に変更されたことを確認するには、次の手順を実行します。

- セキュリティ & コンプライアンス センターで、脅威管理ポリシーのスパム対策に移動し、接続フィルター ポリシー (常にオン) の横にあるドロップダウンをクリックし、設定 \>  \>  \> を確認します。 

- Exchange Online PowerShell またはスタンドアロンの EOP PowerShell で、次のコマンドを実行し、設定を確認します。

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- IP 許可一覧のエントリからテスト メッセージを送信します。

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 許可一覧に関するその他の考慮事項

以下のセクションでは、IP 許可一覧を構成する際に知る必要があるその他の項目を示します。

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>利用可能な範囲外の CIDR IP のスパム フィルター処理をスキップする

この記事で前述したように、CIDR IP は IP 許可一覧のネットワーク マスク /24 ~ /32 でのみ使用できます。 /1 ~ /23 の範囲のソース メール サーバーからのメッセージに対するスパム フィルター処理をスキップするには、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を使用する必要があります。 ただし、/1 ~ /23 CIDR IP 範囲の IP アドレスが Microsoft 独自のブロック リストまたはサード パーティ製のブロック リストに表示される場合、メッセージはブロックされます。ただし、可能な限りこれを行うのはお勧めしません。

潜在的な問題を十分に認識したので、次の設定 (少なくとも) を使用してメール フロー ルールを作成し、これらの IP アドレスからのメッセージがスパム フィルター処理をスキップする必要があります。

- ルールの条件 **:** 送信者の IP アドレスがこれらの範囲または完全に一致する場合に、このルールを適用します \>  \>  \> (CIDR IP を /1 ~ /23 ネットワーク マスクで入力します)。

- ルールの処理: **メッセージのプロパティを変更** \> **する Spam Confidence Level (SCL)** \> **バイパス スパム フィルターを設定します**。

ルールの監査、ルールのテスト、特定の期間のルールのアクティブ化、その他の選択を行います。 ルールを施行する前に一定期間ルールをテストすることをお勧めします。 詳細については [、「Exchange Online でのメール フロー ルールの管理」を参照してください](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>同じソースから選択した電子メール ドメインに対するスパム フィルター処理をスキップする

通常、IP 許可一覧に IP アドレスまたはアドレス範囲を追加すると、その電子メール ソースからのすべての受信メッセージが信頼されます。 しかし、そのソースが複数のドメインから電子メールを送信し、それらのドメインの一部に対するスパム フィルタリングをスキップし、他のドメインではスキップしない場合は、どうなるでしょうか。 これを行うのに IP 許可一覧を単独で使用することはできませんが、IP 許可一覧とメール フロー ルールを組み合わせて使用できます。

たとえば、送信元の電子メール サーバー 192.168.1.25 は、ドメイン contoso.com、fabrikam.com、および tailspintoys.com から電子メールを送信しますが、fabrikam.com の送信者からのメッセージに対するスパム フィルター処理のみをスキップします。 これを行うには、次の手順を使用します。

1. IP 許可一覧に 192.168.1.25 を追加します。

2. 次の設定を使用してメール フロー ルールを構成します (少なくとも次の設定を行います)。

   - ルールの条件 **:** 送信者の IP アドレスがこれらの範囲内にある場合、または \>  \>  \> 192.168.1.25 (前の手順で IP 許可一覧に追加した IP アドレスまたはアドレス範囲と同じ) と完全に一致する場合は、このルールを適用します。

   - ルールの処理: **メッセージのプロパティを変更** \> **する Spam Confidence Level (SCL)** \> **0 を設定します**。

   - ルールの例外: **送信者** \> **のドメインfabrikam.com** (スパム フィルター処理をスキップするドメイン \> のみ) です。

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>IP 許可一覧のソースからのメッセージがフィルター処理されるシナリオ

IP 許可一覧の電子メール サーバーからのメッセージは、次のシナリオでは引き続きスパム フィルターの対象になります。

- IP 許可一覧の IP アドレスは、Microsoft 365 の任意のテナント内のオンプレミスの IP ベースの受信コネクタ (このテナント Aと呼ぶ) にも構成され、最初にメッセージが検出されたテナント A と EOP サーバーは、Microsoft データセンターの同じ *Active* Directory フォレストに存在します。 このシナリオでは **、IPV:CAL** がメッセージのスパム対策メッセージ ヘッダー [(メッセージ](anti-spam-message-headers.md)がスパム フィルターをバイパスしたことを示す) に追加されますが、メッセージはスパム フィルター処理の対象になります。

- IP 許可一覧を含むテナントと、最初にメッセージが検出された EOP サーバーの両方が、Microsoft データセンター内の異なる *Active* Directory フォレストにあることが発生します。 このシナリオでは **、IPV:CAL** はメッセージ ヘッダーに追加されないので、メッセージはスパム フィルタリングの対象になります。

これらのシナリオのどちらかが発生した場合は、次の設定 (少なくとも) を使用してメール フロー ルールを作成し、問題のある IP アドレスからのメッセージがスパム フィルター処理をスキップします。

- ルールの条件:**送信者** の IP アドレスが次の範囲に含まれる場合、または完全に一致する (IP アドレスまたは IP アドレス) 場合は、この \>  \>  \> ルールを適用します。

- ルールの処理: **メッセージのプロパティを変更** \> **する Spam Confidence Level (SCL)** \> **バイパス スパム フィルターを設定します**。

## <a name="new-to-microsoft-365"></a>Microsoft 365 を使用する場合

****

![LinkedIn Learning の ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365 の** 新機能の短いアイコン LinkedIn Learning によって **提供される、Microsoft 365** 管理者と IT プロ向け無料のビデオ コースをご覧ください。
