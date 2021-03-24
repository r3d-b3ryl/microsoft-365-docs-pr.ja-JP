---
title: Exchange Online メールボックスで迷惑メール設定を構成する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online メールボックスで迷惑メール設定を構成する方法について説明します。 これらの設定の多くは、Outlook または Outlook on the web のユーザーが利用できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f7e5d99198e539a46c240fadd2a7a8201236026f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065372"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online メールボックスで迷惑メール設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Online にメールボックスがある Microsoft 365 組織では、組織のスパム対策設定は Exchange Online Protection (EOP) によって制御されます。 詳細については [、「EOP でのスパム対策保護」を参照してください](anti-spam-protection.md)。

ただし、管理者が Exchange Online の個々のメールボックスに対して構成できる特定のスパム対策設定も用意されています。

- **迷惑メール ルールを有効** または無効にする: 迷惑メール ルールは、すべてのメールボックスで既定で有効になっている迷惑メール ルールという名前の非表示の受信トレイ ルールです。 迷惑メール ルールは、次の機能を制御します。

  - スパム対策ポリシーに基づいてメッセージを迷惑メール フォルダーに移動する **:** スパム対策ポリシーが [スパムフィルターの評決の迷惑メール フォルダーにメッセージを移動する] アクションで構成されている場合、迷惑メール フィルター ルールは、メッセージがメールボックスに配信された後に迷惑メール フォルダーにメッセージを移動します。 スパム対策ポリシーのスパム フィルターの評決の詳細については、「EOP でスパム対策ポリシーを構成する」 [を参照してください](configure-your-spam-filter-policies.md)。 同様に、0 時間自動削除 (ZAP) によって配信されたメッセージがスパムまたはフィッシングと判断された場合、迷惑メール フィルター ルールは、メッセージを迷惑メール フォルダースパム フィルターの評決アクションに移動する迷惑メール フォルダーに移動します。 ZAP の詳細については、「Exchange Online の [ゼロ時間自動削除 (ZAP)」を参照してください](zero-hour-auto-purge.md)。

  - **Outlook** または Outlook on the web でユーザーが自分で構成する迷惑メール設定 : セーフリスト コレクションは、各メールボックスの差出人セーフ リスト、安全な受信者リスト、および受信拒否リストです。 これらのリストのエントリは、迷惑メール ルールがメッセージを受信トレイまたは迷惑メール フォルダーに移動するかどうかを決定します。 ユーザーは、Outlook または Outlook on the web (旧称: Outlook Web App) で自分のメールボックスのセーフリスト コレクションを構成できます。 管理者は、任意のユーザーのメールボックスでセーフリスト コレクションを構成できます。

メールボックスで迷惑メール ルールが有効になっている場合、EOP はスパム フィルターの評決アクションに基づいてメッセージを迷惑メール フォルダーに移動したり、メールボックスの [受信拒否] リストにメッセージを移動したり、迷惑メール フォルダー (メールボックスの差出人セーフ リストに基づく) にメッセージを配信したりすることはできません。

 メールボックスで迷惑メール ルールが無効になっている場合、EOP はスパム フィルターの評決アクションに基づいてメッセージを迷惑メール フォルダーに移動できません。メッセージを迷惑メール フォルダーまたはメールボックスのセーフリスト コレクションに移動することはできません。

管理者は Exchange Online PowerShell を使用して、メールボックスの迷惑メール ルールの状態を無効、有効、および表示できます。 管理者は、Exchange Online PowerShell を使用して、メールボックスのセーフリスト コレクション内のエントリ (差出人セーフ リスト、安全な受信者リスト、および受信拒否リスト) を構成できます。

> [!NOTE]
> ユーザーが自分の差出人セーフ リストに追加した送信者からのメッセージは、EOP の一部として接続フィルター処理をスキップします (SCL は -1 です)。 ユーザーが Outlook の [差出人セーフ リストにエントリを追加する] を防ぐには、この記事の後半の  [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」に記載されているグループ ポリシーを使用します。 ポリシー フィルター、コンテンツ フィルター、および 365 Officeの Defender は、引き続きメッセージに適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- この記事の手順を実行するには、Exchange Online PowerShell のみを使用できます。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行するには、Exchange Online でアクセス許可を割り当てる必要があります。 具体的には、メール受信者の役割 (既定では[組織の管理]、[受信者の管理]、および [カスタム メール受信者] 役割グループに割り当てられている)、または [ユーザーオプション] 役割 (既定では [組織の管理] 役割グループと [ヘルプ デスク] 役割グループに割り当てられている) が必要です。     Exchange Online の役割グループにユーザーを追加するには、「Exchange Online で役割 [グループを変更する」を参照してください](/Exchange/permissions-exo/role-groups#modify-role-groups)。 既定のアクセス許可を持つユーザーは [、Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)にアクセスできる限り、自分のメールボックスで同じ手順を実行できます。

- EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。

- 共有メールボックスの差出人セーフ リストは、Azure ADおよび EOP に設計によって同期されません。

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Exchange Online PowerShell を使用してメールボックス内の迷惑メール ルールを有効または無効にする

> [!NOTE]
> Outlook (Exchange キャッシュ モードで) または Web 上の Outlook で開かれているメールボックスで迷惑メール ルールを無効にするには、 **Set-MailboxJunkEmailConfiguration** コマンドレットのみを使用できます。 メールボックスが開かされていない場合は、エラーが表示されます。このエラーを一括操作で抑制する場合は `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration** コマンドに追加できます。

メールボックスで迷惑メール ルールを有効または無効にするには、次の構文を使用します。

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity <MailboxIdentity> -Enabled <$true | $false>
```

次の例では、Ori Epstein のメールボックスで迷惑メール ルールを無効にします。

```PowerShell
Set-MailboxJunkEmailConfiguration -Identity "Ori Epstein" -Enabled $false
```

次の例では、組織内のすべてのユーザーのメールボックスの迷惑メール ルールを無効にします。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -Enabled $false}
```

構文とパラメーターの詳細については [、「Set-MailboxJunkEmailConfiguration」を参照してください](/powershell/module/exchange/set-mailboxjunkemailconfiguration)。

> [!NOTE]
>
> - ユーザーがメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが表示される場合があります。 一括操作でこのエラーを抑制するには `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** します。
>
> - 迷惑メール ルールを無効にした場合でも、Outlook 迷惑メール フィルター (構成方法に応じて) は、メッセージがスパムであるかどうかを判断し、メッセージを自身のスパムの評決とメールボックスのセーフリスト コレクションに基づいて受信トレイまたは迷惑メール フォルダーに移動することもできます。 詳細については、この記事の [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」セクションを参照してください。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

メールボックスで迷惑メール ルールを正常に有効または無効にしたことを確認するには、次のいずれかの手順を使用します。

- メールボックスの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行して _\<MailboxIdentity\>_ Enabled プロパティの **値を** 確認します。

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell を使用してメールボックスのセーフリスト コレクションを構成する

メールボックスのセーフリスト コレクションには、信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リストが含まれています。 既定では、ユーザーは Outlook または Outlook on the web で自分のメールボックスでセーフリスト コレクションを構成できます。 管理者は、 **Set-MailboxJunkEmailConfiguration** コマンドレットで対応するパラメーターを使用して、ユーザーのメールボックスのセーフリスト コレクションを構成できます。 次の表に、これらのパラメーターの説明を示します。

****

|パラメーター on Set-MailboxJunkEmailConfiguration|Outlook on the Web 設定|
|---|---|
|_BlockedSendersAndDomains_|**次の送信者またはドメインからのメールを [迷惑メール] フォルダーに移動する**|
|_ContactsTrusted_|**自分の連絡先からのメールを信頼する**|
|_TrustedListsOnly_|**[差出人セーフ リストとドメイン] リストと [セーフ メール リスト] のアドレスからのメールのみを信頼する**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**これらの送信者から迷惑メール フォルダーにメールを移動しない**|
|

<sup>\*</sup>**注**:

- Exchange Online **では、差** 出人セーフ リストまたは _TrustedSendersAndDomains_ パラメーターのドメイン エントリは認識されないので、電子メール アドレスのみを使用します。 ディレクトリ同期を使用するスタンドアロン EOP では、ドメイン エントリは既定では同期されませんが、ドメインの同期を有効にできます。 詳細については [、「KB3019657」を参照してください](https://support.microsoft.com/help/3019657)。

- **Set-MailboxJunkEmailConfiguration** コマンドレット _(TrustedRecipientsAndDomains_ パラメーターが機能しない) を使用して、安全な受信者リストを直接変更することはできません。 信頼できる差出人のリストを変更し、それらの変更が信頼できる宛先のリストに同期されます。

メールボックスにセーフリスト コレクションを構成するには、次の構文を使用します。

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

複数の値を入力し _、BlockedSendersAndDomains_ および _TrustedSendersAndDomains_ パラメーターの既存のエントリを上書きするには、次の構文を使用します `"<Value1>","<Value2>"...` 。 他の既存のエントリに影響を与えることなく 1 つ以上の値を追加または削除するには、次の構文を使用します。 `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

以下の例では、Ori Epstein のメールボックスのセーフリスト コレクションの次の設定を構成します。

- [受信拒否] shopping@fabrikam.com に値を追加します。

- [差出人セーフ リスト chris@fourthcoffee.com 受信者の一覧から値を削除します。

- 信頼できる差出人として扱われるように [連絡先] フォルダー内の連絡先を構成する。

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

次の例では、組織内の全ユーザーのメールボックスの受信拒否リストから contoso.com ドメインを削除します。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

構文とパラメーターの詳細については [、「Set-MailboxJunkEmailConfiguration」を参照してください](/powershell/module/exchange/set-mailboxjunkemailconfiguration)。

> [!NOTE]
>
> - ユーザーが自分のメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが表示される場合があります。 一括操作でこのエラーを抑制するには `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** します。
>
> - メールボックスで迷惑メール ルールが無効になっている場合でも、セーフリスト コレクションを構成できます。Outlook 迷惑メール フィルターはメッセージを受信トレイまたは迷惑メール フォルダーに移動できます。 詳細については、この記事の [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」セクションを参照してください。
>
> - Outlook 迷惑メール フィルターには、追加のセーフリスト コレクション設定があります (たとえば、電子メールのユーザーを [差出人セーフ リストに自動的 **に追加** する] など)。 詳細については、「迷惑メール フィルター [を使用して表示されるメッセージを制御する」を参照してください](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

メールボックスにセーフリスト コレクションを正常に構成したことを確認するには、次のいずれかの手順を使用します。

- メールボックスの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行してプロパティ _\<MailboxIdentity\>_ 値を確認します。

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  値の一覧が長すぎる場合は、次の構文を使用します。

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Outlook での迷惑メール設定について

Outlook で使用できる、クライアント側の迷惑メール フィルター設定を有効にしたり、無効ににしたり、構成したりするには、グループ ポリシーを使用します。 詳細については、「管理用テンプレート ファイル (ADMX/ADML) および Office カスタマイズ ツール for [Microsoft 365 Apps for enterprise、Office 2019、Office 2016」](https://www.microsoft.com/download/details.aspx?id=49030)および「グループ ポリシーを使用して差出人セーフ リストなどの迷惑メール設定を展開する方法」を参照してください。 [](https://support.microsoft.com/help/2252421)

Outlook 迷惑メール フィルターを既定値に設定すると、[ホーム 迷惑メール電子メール オプション オプション] で自動フィルター処理を行わないと \>  \>  \> 、Outlook はマッサージをスパムとして分類しようとはしませんが、引き続きセーフリスト コレクション (差出人セーフ リスト、セーフ 受信者リスト、および受信拒否リスト) を使用して、配信後に迷惑メール フォルダーにメッセージを移動します。 これらの設定の詳細については、「迷惑メール [フィルターの概要」を参照してください](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。

Outlook の迷惑メール フィルターが **[低]** または **[高]** に設定されている場合、Outlook の迷惑メール フィルターでは、独自の SmartScreen フィルター テクノロジを使用して、迷惑メールを識別し、[迷惑メール] フォルダーに移動します。 このスパム分類は、EOP によって決定されるスパム信頼レベル (SCL) とは別です。 実際、Outlook は EOP からの SCL を無視します (EOP がスパム フィルター処理をスキップするようにメッセージをマークしない限り)、独自の条件を使用してメッセージがスパムであるかどうかを判断します。 もちろん、EOP と Outlook からのスパムの評決は同じ可能性があります。 これらの設定の詳細については、「迷惑メール フィルター [で保護レベルを変更する」を参照してください](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。

> [!NOTE]
> 2016 年 11 月、Microsoft は Exchange および Outlook の SmartScreen フィルターのスパム定義更新プログラムの作成を停止しました。 既存の SmartScreen スパム定義は残されたが、その有効性は時間の流れる間に低下する可能性が高い。 詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)」 をご覧ください。

そのため、Outlook 迷惑メール フィルターは、メールボックス内で迷惑メール ルールが無効になっている場合でも、メールボックスのセーフリスト コレクションと独自のスパム分類を使用して、迷惑メール フォルダーにメッセージを移動できます。

Outlook と Web 上の Outlook の両方で、セーフリスト コレクションがサポートされます。 セーフリスト コレクションは Exchange Online メールボックスに保存されます。そのため、Outlook のセーフリスト コレクションへの変更は Outlook on the web に表示され、その逆も同様です。

## <a name="limits-for-junk-email-settings"></a>迷惑メール設定の制限

ユーザーのメールボックスに格納されているセーフリスト コレクション (差出人セーフ リスト、セーフ 受信者リスト、および受信拒否リスト) も EOP に同期されます。 ディレクトリ同期を使用すると、セーフリスト コレクションは Azure AD。

- ユーザーのメールボックス内のセーフリスト コレクションの制限は 510 KB で、これにはすべてのリストと追加の迷惑メール フィルター設定が含まれます。 ユーザーがこの制限を超えると、次のような Outlook エラーが表示されます。

  > サーバーの迷惑メール リストに追加できない/追加できません。 サーバーで許可されているサイズを超えました。 サーバー上の迷惑メール フィルターは、迷惑メール リストがサーバーで許可されるサイズに縮小されるまで無効になります。

  この制限と変更方法の詳細については [、「KB2669081」を参照してください](https://support.microsoft.com/help/2669081)。

- EOP の同期セーフリスト コレクションには、次の同期制限があります。

  - 連絡先からの信頼メールが有効になっている場合、差出人セーフ リスト、安全な受信者リスト、外部連絡先の合計エントリ数は 1024 です。
  - [ブロックされた送信者] リストと [ブロックされたドメイン] リストの合計エントリ数は 500 です。

  1024 エントリの制限に達すると、次のことが発生します。

  - PowerShell と Outlook on the web のエントリの受け入れは停止しますが、エラーは表示されません。

    Outlook ユーザーは、Outlook の制限値 510 KB に達するまで、引き続き 1024 以上のエントリを追加できます。 メールボックスに配信する前に EOP フィルターがメッセージをブロックしない限り、Outlook ではこれらの追加エントリを使用できます (メール フロー ルール、スプーフィング対策など)。

- ディレクトリ同期では、エントリは Azure AD順に同期されます。

  1. 連絡先からのメールの **信頼が有効になっている場合は、連絡先に** メールを送信します。
  2. 差出人セーフ リストとセーフ 受信者リストは、最初の 1024 エントリに対して変更が行われたたびに、アルファベット順に結合、重複、および並べ替えされます。

  最初の 1024 エントリが使用され、関連する情報がメッセージ ヘッダーにスタンプされます。

  Azure AD に同期されていない 1024 を超えるエントリは Outlook (Outlook on the web ではなく) によって処理され、メッセージ ヘッダーには情報がスタンプされません。

ご覧のように、[連絡先からのメールの信頼] 設定を有効にすると、同期できる差出人セーフ リストとセーフ 受信者の数が減少します。 これが懸念される場合は、グループ ポリシーを使用してこの機能をオフにすることをお勧めします。

- ファイル名: outlk16.opax
- ポリシー設定: **連絡先からの電子メールを信頼する**