---
title: Exchange Online メールボックスで迷惑メール設定を構成する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online メールボックスで迷惑メール設定を構成する方法について説明します。 これらの設定の多くは、Outlook または Outlook on the web のユーザーが使用できます。
ms.openlocfilehash: 5469143e0a924478e0bbb7285ac607095d4a169f
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659728"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online メールボックスで迷惑メール設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Exchange Online にメールボックスがある Microsoft 365 組織では、組織のスパム対策設定は Exchange Online Protection (EOP) によって制御されます。 詳細については [、「EOP でのスパム対策保護」を参照してください](anti-spam-protection.md)。

ただし、管理者が Exchange Online の個々のメールボックスに対して構成できる特定のスパム対策設定も用意されています。

- **迷惑メール ルールを** 有効または無効にする : 迷惑メール ルールは、すべてのメールボックスで既定で有効になっている迷惑メール ルールという名前の非表示の受信トレイ ルールです。 迷惑メール ルールは、次の機能を制御します。

  - スパム対策ポリシーに基づいてメッセージを [迷惑メール] フォルダーに移動 **する:** スパム対策ポリシーがスパムフィルターの条件として [迷惑メール] フォルダーに移動するアクションを使用して構成されている場合、迷惑メール フィルター ルールは、メッセージがメールボックスに配信された後、そのメッセージを [迷惑メール] フォルダーに移動します。 スパム対策ポリシーでのスパム フィルターの条件の詳細については [、「EOP](configure-your-spam-filter-policies.md)でスパム対策ポリシーを構成する」を参照してください。 同様に、ゼロアワー自動消去 (ZAP) によって、配信されたメッセージがスパムまたはフィッシングと判断された場合、迷惑メール フィルター ルールは、メッセージを [迷惑メール] フォルダーのスパム フィルターの判断アクションに移動するために [迷惑メール] フォルダーに移動します。 ZAP の詳細については、Exchange Online のゼロアワー自動消去 [(ZAP) を参照してください](zero-hour-auto-purge.md)。

  - **ユーザー** が Outlook または Outlook on the web で自分自身のために構成する迷惑メール設定: セーフリスト コレクションは、各メールボックスの差出人セーフ リスト、宛先セーフ リスト、および受信拒否リストです。 これらの一覧のエントリは、迷惑メール ルールがメッセージを受信トレイまたは迷惑メール フォルダーに移動するかどうかを決定します。 ユーザーは、Outlook または Outlook on the web (旧称: Outlook Web App) で、自分のメールボックスのセーフリスト コレクションを構成できます。 管理者は、任意のユーザーのメールボックスにセーフリスト コレクションを構成できます。

メールボックスで迷惑メール ルールが有効になっている場合、EOP はスパム フィルターの条件アクションに基づいてメッセージを [迷惑メール] フォルダーに移動するか、メールボックスの受信拒否リストにメッセージを移動し、(メールボックスの差出人セーフ リストに基づいて) 迷惑メール フォルダーにメッセージが配信されるのを防ぐことが可能です。

 メールボックスで迷惑メール ルールが無効になっている場合、EOP はスパム フィルターの確認アクションに基づいてメッセージを [迷惑メール] フォルダーに移動できません。メッセージを [迷惑メール] フォルダーまたはメールボックスのセーフリスト コレクションに移動します。

管理者は、Exchange Online PowerShell を使用して、メールボックスの迷惑メール ルールの無効化、有効化、および状態の表示を行えます。 管理者は、Exchange Online PowerShell を使用して、メールボックスのセーフリスト コレクション (差出人セーフ リスト、宛先セーフ リスト、受信拒否リスト) のエントリを構成できます。

> [!NOTE]
> ユーザーが自分の差出人セーフ リストに追加した送信者からのメッセージは、EOP の一部として接続フィルターをスキップします (SCL は -1)。 ユーザーが Outlook の差出人セーフ リストにエントリを追加するのを防ぐには、この記事の後半の  [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」に記載されているグループ ポリシーを使用します。 ポリシー フィルター、コンテンツ フィルター、および 365 Officeの Defender は、引き続きメッセージに適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- この記事の手順を実行するには、Exchange Online PowerShell のみを使用できます。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行する前に、Exchange Online でアクセス許可を割り当てる必要があります。 具体的には、"Mail **Recipients/** メール受信者" 役割 (既定では **"Organization Management/** 組織の管理"、"Recipient **Management/** 受信者の管理"、および **"Custom Mail Recipients/** カスタム メール受信者" 役割グループに割り当てられている) または **"User Options/** ユーザー オプション" 役割 (既定では **"Organization Management/** 組織の管理" 役割グループと **"Help Desk/** ヘルプ デスク" 役割グループに割り当てられている) が必要です。 Exchange Online の役割グループにユーザーを追加するには、「Exchange Online で役割グループを変更 [する」を参照してください](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。 既定のアクセス許可を持つユーザーは、Exchange Online PowerShell にアクセスできる限り、自分のメールボックスで同じ [手順を実行できます](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)。

- EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。

- 共有メールボックスの差出人セーフ リストは、設計上 Azure AD EOP に同期されません。

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Exchange Online PowerShell を使用してメールボックスの迷惑メール ルールを有効または無効にする

> [!NOTE]
> Outlook (Exchange キャッシュ モードで) または Web 上の Outlook で開かれているメールボックスで迷惑メール ルールを無効にするには、 **Set-MailboxJunkEmailConfiguration** コマンドレットのみを使用できます。 メールボックスが開いていない場合は、次のエラーが表示されます。一括操作でこのエラーを抑制する場合は `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration** コマンドに追加できます。

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

構文およびパラメーターの詳細については [、「Set-MailboxJunkEmailConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。

> [!NOTE]
>
> - ユーザーがメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが発生する可能性があります。 一括操作でこのエラーを抑制するには `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** します。
>
> - 迷惑メール ルールを無効にした場合でも、Outlook 迷惑メール フィルター (構成方法に応じて) は、メッセージがスパムであるかどうかを判断し、メッセージ自身のスパムの判断とメールボックスのセーフリスト コレクションに基づいて、メッセージを [受信トレイ] フォルダーまたは [迷惑メール] フォルダーに移動できます。 詳細については、この記事の [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」セクションを参照してください。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

メールボックスで迷惑メール ルールを正常に有効または無効にしたことを確認するには、次のいずれかの手順を使用します。

- メールボックスの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行して Enabled プロパティの値 _\<MailboxIdentity\>_ **を** 確認します。

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell を使用してメールボックスのセーフリスト コレクションを構成する

メールボックスのセーフリスト コレクションには、信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リストが含まれています。 既定では、ユーザーは Outlook または Outlook on the web の自分のメールボックスでセーフリスト コレクションを構成できます。 管理者は、 **Set-MailboxJunkEmailConfiguration** コマンドレットで対応するパラメーターを使用して、ユーザーのメールボックスのセーフリスト コレクションを構成できます。 次の表に、これらのパラメーターの説明を示します。

****

|パラメーターのSet-MailboxJunkEmailConfiguration|Outlook on the web の設定|
|---|---|
|_BlockedSendersAndDomains_|**次の送信者またはドメインからのメールを [迷惑メール] フォルダーに移動する**|
|_ContactsTrusted_|**自分の連絡先からのメールを信頼する**|
|_TrustedListsOnly_|**信頼できる差出人とドメインのリストと安全なメール リストのアドレスからのメールのみを信頼する**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**これらの送信者から [迷惑メール] フォルダーにメールを移動しない**|
|

<sup>\*</sup>**メモ**:

- Exchange Online **では、信頼** できる差出人のリストまたは _TrustedSendersAndDomains_ パラメーターのドメイン エントリは認識されないので、電子メール アドレスのみを使用します。 ディレクトリ同期を使用するスタンドアロン EOP では、ドメイン エントリは既定では同期されませんが、ドメインの同期を有効にできます。 詳細については [、KB3019657 を参照](https://support.microsoft.com/help/3019657)してください。

- **Set-MailboxJunkEmailConfiguration** コマンドレットを使用して宛先セーフ リストを直接変更することはできません _(TrustedRecipientsAndDomains_ パラメーターは機能しません)。 信頼できる差出人のリストを変更し、それらの変更が信頼できる宛先のリストに同期されます。

メールボックスにセーフリスト コレクションを構成するには、次の構文を使用します。

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

複数の値を入力し _、BlockedSendersAndDomains_ および _TrustedSendersAndDomains_ パラメーターの既存のエントリを上書きするには、次の構文を使用します `"<Value1>","<Value2>"...` 。 他の既存のエントリに影響を及ぼさずに 1 つ以上の値を追加または削除するには、次の構文を使用します。 `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

以下の例では、Ori Epstein のメールボックスのセーフリスト コレクションの次の設定を構成します。

- 受信拒否リストshopping@fabrikam.com値を追加します。

- 差出人セーフ リストchris@fourthcoffee.com宛先セーフ リストから値を削除します。

- 信頼できる差出人として扱われるように [連絡先] フォルダー内の連絡先を構成する。

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

次の例では、組織内の全ユーザーのメールボックスの受信拒否リストから contoso.com ドメインを削除します。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

構文およびパラメーターの詳細については [、「Set-MailboxJunkEmailConfiguration」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-mailboxjunkemailconfiguration)。

> [!NOTE]
>
> - ユーザーがメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが発生する可能性があります。 一括操作でこのエラーを抑制するには `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** します。
>
> - メールボックスで迷惑メール ルールが無効になっている場合でも、セーフリスト コレクションを構成できます。Outlook 迷惑メール フィルターは、受信トレイまたは迷惑メール フォルダーにメッセージを移動できます。 詳細については、この記事の [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」セクションを参照してください。
>
> - Outlook 迷惑メール フィルターには、追加のセーフリスト コレクション設定があります (たとえば、メールを受信したユーザーを [差出人セーフ リスト **に自動的に追加する] など**)。 詳細については、「迷惑メール フィルター [を使用して表示されるメッセージを制御する」を参照してください](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

メールボックスにセーフリスト コレクションを正常に構成したことを確認するには、次のいずれかの手順を使用します。

- メールボックスの名前、エイリアス、または電子メール アドレスに置き換え、次のコマンドを実行してプロパティ _\<MailboxIdentity\>_ の値を確認します。

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  値の一覧が長すぎる場合は、次の構文を使用します。

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Outlook での迷惑メール設定について

Outlook で使用できる、クライアント側の迷惑メール フィルター設定を有効にしたり、無効ににしたり、構成したりするには、グループ ポリシーを使用します。 詳細については、「Microsoft [365 Apps for enterprise、Office 2019、Office 2016](https://www.microsoft.com/download/details.aspx?id=49030)用の管理用テンプレート ファイル (ADMX/ADML) および Office[](https://support.microsoft.com/help/2252421)カスタマイズ ツール」および「グループ ポリシーを使用して差出人セーフ リストなどの迷惑メール設定を展開する方法」を参照してください。

When the Outlook Junk Email Filter is set to the default value **No automatic filtering** in **Home** \> **Junk** \> **Junk E-Mail Options,** Outlook doesn't attempt to classify the spam, but still uses the \> safelist collection (the Safe Senders list, Safe Recipients list, and Blocked Senders list) to move messages to the Junk Email folder after delivery. これらの設定の詳細については、「迷惑メール フィルターの概要 [」を参照してください](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。

Outlook の迷惑メール フィルターが **[低]** または **[高]** に設定されている場合、Outlook の迷惑メール フィルターでは、独自の SmartScreen フィルター テクノロジを使用して、迷惑メールを識別し、[迷惑メール] フォルダーに移動します。 このスパム分類は、EOP によって決定される SCL (Spam Confidence Level) とは別の分類です。 実際、Outlook は EOP からの SCL を無視し (EOP がスパム フィルタリングをスキップするようにメッセージをマークしない限り)、独自の条件を使用してメッセージがスパムであるかどうかを判断します。 もちろん、EOP と Outlook からのスパムの検出は同じ可能性があります。 これらの設定の詳細については、「迷惑メール フィルター」の「保護レベルを変更 [する」を参照してください](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。

> [!NOTE]
> 2016 年 11 月に、Microsoft は Exchange と Outlook の SmartScreen フィルターのスパム定義の更新の生成を停止しました。 既存の SmartScreen スパム定義は残っていますが、その有効性は時間の流れる中で低下する可能性があります。 詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)」 をご覧ください。

そのため、Outlook 迷惑メール フィルターは、メールボックスのセーフリスト コレクションと独自のスパム分類を使用して、迷惑メール ルールがメールボックスで無効になっている場合でも、メッセージを [迷惑メール] フォルダーに移動できます。

Outlook と Web 上の Outlook の両方で、セーフリスト コレクションがサポートされます。 セーフリスト コレクションは Exchange Online メールボックスに保存されます。そのため、Outlook のセーフリスト コレクションに対する変更は Outlook on the web に表示され、その逆も同様です。

## <a name="limits-for-junk-email-settings"></a>迷惑メール設定の制限

ユーザーのメールボックスに格納されているセーフリスト コレクション (差出人セーフ リスト、宛先セーフ リスト、受信拒否リスト) も EOP と同期されます。 ディレクトリ同期を使用すると、セーフリスト コレクションは Azure AD。

- ユーザーのメールボックス内のセーフリスト コレクションの上限は 510 KB で、これにはすべてのリストに加えて、追加の迷惑メール フィルター設定が含まれます。 ユーザーがこの制限を超えると、次のような Outlook エラーが表示されます。

  > Cannot/Unable add to the server Junk E-mail lists. サーバーで許可されているサイズを超えました。 迷惑メール リストがサーバーで許可されているサイズに縮小されるまで、サーバーの迷惑メール フィルターは無効になります。

  この制限と変更方法の詳細については [、KB2669081 を参照](https://support.microsoft.com/help/2669081)してください。

- EOP の同期されたセーフリスト コレクションには、次の同期制限があります。

  - 連絡先からの信頼メールが有効な場合、差出人セーフ リスト、宛先セーフ リスト、および外部連絡先の合計エントリ数は 1,024 です。
  - [受信拒否リスト] および [受信拒否ドメイン] リストの合計エントリ数は 500 です。

  1024 エントリの制限に達すると、次のことが発生します。

  - PowerShell と Outlook on the web のエントリの受け入れは一覧によって停止されますが、エラーは表示されません。

    Outlook ユーザーは、Outlook の制限である 510 KB に達するまで、1024 を超えるエントリを引き続き追加できます。 メールボックスに配信する前に EOP フィルターがメッセージをブロックしない限り (メール フロー ルール、スプーフィング対策など)、Outlook ではこれらの追加のエントリを使用できます。

- ディレクトリ同期では、エントリは Azure AD次の順序で同期されます。

  1. 連絡先からのメール **が信頼できる場合は、連絡先に** メールを送信します。
  2. 差出人セーフ リストと宛先セーフ リストは、最初の 1024 エントリに変更が行われたときにアルファベット順に結合、重複、および並べ替えされます。

  最初の 1024 エントリが使用され、関連する情報がメッセージ ヘッダーにスタンプされます。

  Azure AD に同期されていない 1024 を超えるエントリは、Outlook (Web 上の Outlook ではなく) によって処理され、メッセージ ヘッダーに情報がスタンプされません。

ご覧のように、[連絡先からの信頼メール] 設定を有効にすると、同期できる信頼できる差出人と信頼できる受信者の数が減少します。 これが問題である場合は、グループ ポリシーを使用してこの機能をオフにすることをお勧めします。

- ファイル名: outlk16.opax
- ポリシー設定: **連絡先からの電子メールを信頼する**
