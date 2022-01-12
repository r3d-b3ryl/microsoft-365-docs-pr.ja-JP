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
description: 管理者は、電子メール サーバーからの電子メールを許可またはブロックExchange Online Protection (EOP) で接続フィルターを構成する方法について学習できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2fbc481468fca8562c11e89b2e6c9dfa6361126a
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2022
ms.locfileid: "61939815"
---
# <a name="configure-connection-filtering"></a>接続フィルターを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


ユーザーがメールボックスを使用Microsoft 365 Exchange Onlineまたはスタンドアロン Exchange Online Protection (EOP) のお客様Exchange Online メールボックスでは、EOP (具体的には既定の接続フィルター ポリシー) で接続フィルターを使用して、IP アドレスによって良い送信元メール サーバーまたは悪い送信元メール サーバーを識別します。 既定の接続フィルター ポリシーの主な構成要素は次のとおりです。

- **IP 許可一覧**: IP アドレスまたは IP アドレス範囲で指定した送信元メール サーバーからの受信メッセージすべてについて、スパム フィルターをスキップします。 これらのソースからのメッセージでスパム フィルター処理が引き続き発生する可能性があるシナリオについては、この記事の後半の [「IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 許可一覧のソースからのメッセージがフィルター処理されるシナリオ」セクションを参照してください。 IP 許可一覧が全体の差出人セーフ リスト戦略に適合する方法の詳細については、「EOP で差出人セーフ リストを作成する」 [を参照してください](create-safe-sender-lists-in-office-365.md)。

- **IP ブロックリスト**: IP アドレスまたは IP アドレス範囲で指定した送信元メール サーバーからの受信メッセージをすべてブロックします。 受信メッセージは拒否され、スパムとしてマークされ、追加のフィルター処理は行われません。 IP ブロック 一覧を全体的にブロックする送信者戦略に適合する方法の詳細については、「EOP でブロック送信者リストを作成する」 [を参照してください](create-block-sender-lists-in-office-365.md)。

- **セーフリスト**: セーフ *リスト* は、顧客構成を必要とする Microsoft データセンターの動的許可リストです。 Microsoft は、サブスクリプションからさまざまなサード パーティのリストへの信頼できる電子メール ソースを識別します。 セーフ リストの使用を有効または無効にします。セーフ リストでソース メール サーバーを構成できません。 セーフ リスト上の電子メール サーバーからの受信メッセージでは、スパム フィルターはスキップされます。

この記事では、Microsoft 365 Microsoft 365 Defender ポータルまたは PowerShell で既定の接続フィルター ポリシーを構成する方法について説明します (Exchange Online PowerShell for Microsoft 365 組織のメールボックスがExchange Online;スタンドアロン EOP PowerShell (メールボックスを使用しない組織Exchange Online)。 EOP が接続フィルターを使用する方法の詳細については、「スパム対策保護」を [参照してください](anti-spam-protection.md)。

> [!NOTE]
> IP 許可一覧、セーフ リスト、および IP ブロック リストは、組織内の電子メールを許可またはブロックする全体的な戦略の 1 部です。 詳細については、「差出人セーフ [リストの作成」および](create-safe-sender-lists-in-office-365.md) 「受信拒否 [リストの作成」を参照してください](create-block-sender-lists-in-office-365.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- <https://security.microsoft.com> で Microsoft 365 Defender ポータルを開きます。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。 スタンドアロンの EOP PowerShell に接続するには、「[Exchange Online Protection PowerShell への接続](/powershell/exchange/connect-to-exchange-online-protection-powershell)」を参照してください。

- この記事の手順を実行する際には、あらかじめ **Exchange Online** でアクセス許可を割り当てる必要があります。
  - 既定の接続フィルター ポリシーを変更するには、組織の管理役割グループまたはセキュリティ管理者役割グループの **メンバーである** 必要があります。
  - 既定の接続フィルター ポリシーへの読み取り専用アクセスでは、グローバル リーダーまたはセキュリティリーダーの役割グループの **メンバーである** 必要があります。

  詳細については、「[Exchange Online のアクセス許可](/exchange/permissions-exo/permissions-exo)」を参照してください。

  **注**:

  - Microsoft 365 管理センターで、対応する Azure Active Directory のロールにユーザーを追加すると、ユーザーには、必要なアクセス許可 _および_ Microsoft 365 のその他の機能に必要なアクセス許可が付与されます。詳しくは、「[管理者のロールについて](../../admin/add-users/about-admin-roles.md)」を参照してください。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) の **閲覧専用の組織管理** の役割グループが この機能への読み取り専用アクセス権も付与します。

- 許可またはブロックする電子メール サーバー (送信者) の送信元 IP アドレスを検索するには、メッセージ ヘッダーの接続 IP (**CIP**) ヘッダー フィールドを確認します。 さまざまな電子メール クライアントでメッセージ ヘッダーを表示するには、「インターネット メッセージ ヘッダーを表示する」を参照[Outlook。](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- IP 許可一覧は IP ブロック リストよりも優先されます (両方のリストのアドレスはブロックされません)。

- IP 許可一覧と IP ブロック リストは、それぞれ最大 1273 エントリをサポートします。エントリは単一の IP アドレス、IP アドレス範囲、または Classless InterDomain Routing (CIDR) IP です。

## <a name="use-the-microsoft-365-defender-portal-to-modify-the-default-connection-filter-policy"></a>既定の接続Microsoft 365 Defenderポリシーを変更するには、このポータルを使用します。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. [スパム **対策ポリシー]** ページで、ポリシーの名前をクリックして、一覧から [接続フィルター ポリシー **(既定)]** を選択します。

3. 表示されるポリシーの詳細フライアウトで、次の設定を構成します。

   - **[説明** ] セクション: [ **名前と説明の編集] をクリックします**。 表示される **[名前と説明の編集]** フライアウトで、[説明] ボックスにオプションの説明テキスト **を入力** します。

     完了したら、**[保存]** をクリックします。

   - **[接続フィルター] セクション**: [接続 **フィルター ポリシーの編集] をクリックします**。 表示されるフライアウトで、次の設定を構成します。

     - **常に次の IP アドレスまたはアドレス範囲** からのメッセージを許可する: これは、IP 許可リストです。 ボックス内をクリックし、値を入力し、Enter キーを押するか、ボックスの下に表示される完全な値を選択します。 有効な値は次のとおりです。
       - 単一 IP: たとえば、192.168.1.1。
       - IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。
       - CIDR IP: たとえば、192.168.0.1/25。 有効なサブネット マスク値は 、/24 ~ /32 です。 /1 ~ /23 のスパム フィルター処理をスキップするには、この記事の後半の「利用可能な範囲外の [CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) のスパム フィルターをスキップする」セクションを参照してください。

       必要な回数だけこの手順を繰り返します。 既存の値を削除するには、削除をクリックします ![[削除] アイコン](../../media/m365-cc-sc-remove-selection-icon.png) 値の隣。

     IP アドレスまたはアドレス範囲を追加するには、ボックス内をクリックして「追加アイコンの追加」と ![ 入力します ](../../media/ITPro-EAC-AddIcon.png) 。 エントリを削除するには、[許可された IP アドレス] でエントリを選択 **し、[** 削除] **をクリック** ![ します ](../../media/scc-remove-icon.png) 。 完了したら、**[保存]** をクリックします。

   - **次の IP アドレスまたはアドレス範囲からの** メッセージを常にブロックする: これは IP ブロック リストです。 [次の IP アドレスまたはアドレス範囲からのメッセージを常に許可する] 設定で説明したように、ボックスに単一の IP、IP 範囲、または **CIDR IP を入力** します。

   - **セーフ リストを有効にする**: スパム フィルターをスキップする既知の優れた送信者を識別するために、セーフ リストの使用を有効または無効にします。 セーフ リストを使用するには、チェック ボックスをオンにします。

   完了したら、**[保存]** をクリックします。

4. ポリシーの詳細ポップアップに戻り、**[閉じる]** をクリックします。

## <a name="use-the-microsoft-365-defender-portal-to-view-the-default-connection-filter-policy"></a>既定の接続Microsoft 365 Defenderポリシーを表示するには、次のポータルを使用します。

1. <https://security.microsoft.com> の Microsoft 365 Defender ポータルで、**[ポリシー]** セクションの **[メールと共同作業]** \> **[ポリシーとルール]** \> **[脅威ポリシー]** \> **[スパム対策]** に移動します。 **[スパム対策ポリシー]** ページに直接移動するには、<https://security.microsoft.com/antispam> を使用します。

2. [スパム **対策ポリシー] ページで** 、ポリシーの一覧に次のプロパティが表示されます。

   - **名前**: この値は、 **既定の接続フィルター ポリシーの接続** フィルター ポリシー (既定) です。
   - **状態**: 既定の接続フィルター **ポリシーでは** 、この値は常にオンです。
   - **優先度**: 既定の接続フィルター **ポリシーの** 場合、この値は最低です。
   - **Type**: 既定の接続フィルター ポリシーでは、この値は空白です。

3. 既定の接続フィルター ポリシーを選択すると、ポリシー設定がフライアウトに表示されます。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>PowerShell Exchange Onlineスタンドアロン EOP PowerShell を使用して既定の接続フィルター ポリシーを変更する

次の構文を使用してください。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**注**:

- 有効な IP アドレスまたはアドレス範囲の値は次のとおりです。
  - 単一 IP: たとえば、192.168.1.1。
  - IP 範囲: たとえば、192.168.0.1-192.168.0.254 です。
  - CIDR IP: たとえば、192.168.0.1/25。 有効なネットワーク マスクの値は、/24 ~ /32 です。
- 指定 *した* 値で既存のエントリを上書きするには、次の構文を使用します `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。
- 他 *の既存のエントリ* に影響を与えることなく IP アドレスまたはアドレス範囲を追加または削除するには、次の構文を使用します `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。
- IP 許可一覧または IP ブロック 一覧を空にするには、値を使用します `$null` 。

次の使用例は、IP 許可一覧と IP ブロック 一覧を、指定した IP アドレスとアドレス範囲で構成します。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

次の使用例は、指定した IP アドレスとアドレス範囲を IP 許可一覧から追加および削除します。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

構文とパラメーターの詳細については [、「Set-HostedConnectionFilterPolicy」を参照してください](/powershell/module/exchange/set-hostedconnectionfilterpolicy)。

## <a name="how-do-you-know-this-worked"></a>実行が適切に行われたことを確認する方法

既定の接続フィルター ポリシーが正常に変更されたことを確認するには、次の手順を実行します。

- Microsoft 365 Defenderポータルの [スパム対策] ページで、ポリシーの名前をクリックして一覧から [接続フィルター ポリシー <https://security.microsoft.com/antispam> **(既定)]** を選択し、設定を確認します。

- PowerShell Exchange Onlineスタンドアロン EOP PowerShell で、次のコマンドを実行し、設定を確認します。

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- IP 許可一覧のエントリからテスト メッセージを送信します。

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 許可一覧に関するその他の考慮事項

次のセクションでは、IP 許可一覧を構成する際に知る必要があるその他の項目を特定します。

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>利用可能な範囲外の CIDR IP のスパム フィルター処理をスキップする

この記事で前述したように、IP 許可一覧では、ネットワーク マスク /24 ~ /32 の CIDR IP のみを使用できます。 /1 ~ /23 範囲の送信元メール サーバーからのメッセージに対するスパム フィルターをスキップするには、Exchange メール フロー ルール (トランスポート ルールとも呼ばれる) を使用する必要があります。 ただし、/1 ~ /23 CIDR IP 範囲の IP アドレスが Microsoft の独自のブロック リストまたはサード パーティ製のブロック リストに表示される場合、メッセージはブロックされますので、可能な限りこれを行う必要はありません。

潜在的な問題を十分に認識したので、(少なくとも) 次の設定でメール フロー ルールを作成して、これらの IP アドレスからのメッセージがスパム フィルター処理をスキップする必要があります。

- ルールの条件:**送信者** IP アドレスがこれらの範囲または完全に一致する場合は、このルールを適用します \>  \>  \> (/1 ~ /23 ネットワーク マスクを使用して CIDR IP を入力します)。
- ルール アクション: **メッセージのプロパティを変更** \> **する スパム信頼レベル (SCL)** \> **バイパス スパム フィルターを設定します**。

ルールの監査、ルールのテスト、特定の期間中のルールのアクティブ化、その他の選択を行います。 ルールを施行する前に一定期間ルールをテストすることをお勧めします。 詳細については、「メール フロー ルール[を管理する」を参照Exchange Online。](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>同じソースからの選択的なメール ドメインのスパム フィルターをスキップする

通常、IP 許可一覧に IP アドレスまたはアドレス範囲を追加すると、そのメール ソースからのすべての受信メッセージを信頼できます。 しかし、そのソースが複数のドメインから電子メールを送信し、それらのドメインの一部に対するスパム フィルターをスキップするが、他のドメインには送信しない場合は、どうなるでしょうか。 IP 許可一覧を単独で使用することはできませんが、メール フロー ルールと組み合わせて IP 許可一覧を使用できます。

たとえば、送信元電子メール サーバー 192.168.1.25 は、ドメイン contoso.com、fabrikam.com、および tailspintoys.com から電子メールを送信しますが、fabrikam.com の送信者からのメッセージに対するスパム フィルター処理のみをスキップする必要があります。 これを行うには、次の手順を使用します。

1. IP 許可一覧に 192.168.1.25 を追加します。

2. 次の設定を使用してメール フロー ルールを構成します (少なくとも)。
   - ルール **の条件:** 送信者 IP アドレスがこれらの範囲にある場合、または \>  \>  \> 192.168.1.25 と完全に一致する場合は、このルールを適用します (前の手順で IP 許可一覧に追加したのと同じ IP アドレスまたはアドレス範囲)。
   - ルールアクション: **メッセージのプロパティを変更** \> **する スパム信頼レベル (SCL)** \> **0 を設定します**。
   - ルール例外:**送信者ドメイン** は fabrikam.com (スパム フィルターをスキップするドメインまたはドメイン \>  \> のみ) です。

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>IP 許可一覧のソースからのメッセージがまだフィルター処理されるシナリオ

IP 許可一覧内の電子メール サーバーからのメッセージは、次のシナリオでスパム フィルター処理の対象になります。

- IP 許可一覧の IP アドレスは、Microsoft 365 のテナント内のオンプレミスの IP ベースの受信コネクタ (このテナント A を呼び出します)、および最初にメッセージを検出したテナント A と EOP サーバーで構成され、両方とも Microsoft データセンター内の同じ *Active* Directory フォレストに存在します。  このシナリオでは **、IPV:CAL** がメッセージのスパム対策メッセージ ヘッダー [(メッセージ](anti-spam-message-headers.md)によってバイパスされたスパム フィルターを示す) に追加されますが、メッセージはスパム フィルター処理の対象です。

- IP 許可一覧と、最初にメッセージが検出された EOP サーバーを含むテナントは、Microsoft データセンター内 *の異なる* Active Directory フォレストに存在します。 このシナリオでは **、IPV:CAL** はメッセージ ヘッダーに追加されないので、メッセージはスパム フィルター処理の対象になります。

これらのシナリオのどちらかが発生した場合は、(少なくとも) 次の設定を使用してメール フロー ルールを作成して、問題のある IP アドレスからのメッセージがスパム フィルター処理をスキップします。

- ルールの条件:**送信者** IP アドレスがこれらの範囲にある場合、または完全に一致する (IP アドレスまたはアドレス) 場合は、この \>  \>  \> ルールを適用します。
- ルール アクション: **メッセージのプロパティを変更** \> **する スパム信頼レベル (SCL)** \> **バイパス スパム フィルターを設定します**。

## <a name="new-to-microsoft-365"></a>新しいMicrosoft 365?

****

LinkedIn ラーニングのショート アイコンです。Office 365 を初めてお使いの場合は         、LinkedIn ラーニングによって提供された Office 365 管理者および IT プロフェッショナル向けの無料のビデオコースをご覧ください。 **新しいMicrosoft 365?** LinkedIn Microsoft 365によって提供される、管理者および **IT** プロ向け無料のビデオ コースラーニング。
