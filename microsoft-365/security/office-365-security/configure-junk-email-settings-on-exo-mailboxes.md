---
title: Exchange Online のメールボックスで迷惑メール設定を構成する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online メールボックスの迷惑メール設定を構成する方法について説明します。 これらの設定の多くは、Outlook または web 上の Outlook でユーザーが使用できます。
ms.openlocfilehash: 55597c45f093a5b9a0b860c6987454f926025e28
ms.sourcegitcommit: 1e9ce51efa583c33625299d17e37f58048a4169c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2020
ms.locfileid: "43804791"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online のメールボックスで迷惑メール設定を構成する

Exchange Online の組織のスパム対策設定は、Exchange Online Protection (EOP) によって制御されます。 詳細については、「[Office 365 のスパム対策保護](anti-spam-protection.md)」を参照してください。

ただし、管理者が Exchange Online の個々のメールボックスで構成できる特定のスパム対策設定もあります。

- **迷惑メールルールを有効または無効**にする: 迷惑メールルールは、すべてのメールボックスで既定で有効になっている迷惑メールルールという名前の非表示の受信トレイルールです。 迷惑メールルールは、次の機能を制御します。

  - スパム**対策ポリシーに基づいて、メッセージを [迷惑メール] フォルダーに移動する**: スパムフィルター verdict の [**メッセージを迷惑メールフォルダーに移動する**] アクションを使用してスパム対策ポリシーを構成した場合、迷惑メールフィルタールールは、メッセージがメールボックスに配信された後に、そのメッセージを迷惑メールフォルダーに移動します。 スパム対策ポリシーの verdicts の詳細については、「 [Office 365 でスパム対策ポリシーを構成する](configure-your-spam-filter-policies.md)」を参照してください。 同様に、自動削除 (ZAP) によって、既に配信されたメッセージのスパムまたはフィッシングが検出されると、迷惑メールフィルタールールはメッセージを迷惑メールフォルダースパムフィルター verdict アクション**に移動する**ための迷惑メールフォルダーに移動します。 ZAP の詳細については、「[ゼロ時間自動削除 (ZAP)-Office 365 のスパムおよびマルウェアに対する保護](zero-hour-auto-purge.md)」を参照してください。
  
  - **ユーザーが outlook または web 上の outlook で自分自身に対して構成する迷惑メール設定**: セーフリスト_コレクション_は、各メールボックスの差出人セーフリスト、宛先セーフリスト、および受信拒否リストです。 これらのリストのエントリは、迷惑メールルールがメッセージを受信トレイまたは迷惑メールフォルダーに移動するかどうかを決定します。 ユーザーは、Outlook または web 上の Outlook (旧称 Outlook Web App) で自分のメールボックスのセーフリストコレクションを構成できます。 管理者は、任意のユーザーのメールボックスでセーフリストコレクションを構成できます。

メールボックスで迷惑メールルールが有効になっている場合、EOP は迷惑メールフォルダーにメッセージを移動することができます。これにより、スパムフィルター処理 verdict アクションに基づいて、メールボックスの迷惑メールフォルダーにメッセージを**移動**したり、受信拒否リストに含まれるメッセージを迷惑メールフォルダーに配信することができなくなります。

 迷惑メールルールがメールボックスで無効になっている場合、EOP は、迷惑メールフォルダーにメッセージを移動することはできません verdict アクションは、迷惑メールフォルダーまたはメールボックス上のセーフリストコレクションに**メッセージを移動**します。

管理者は、Exchange Online PowerShell を使用して、メールボックスの迷惑メールルールの状態を無効、有効にし、表示することができます。 管理者は、Exchange Online PowerShell を使用して、メールボックス (差出人セーフリスト、宛先セーフリスト、および受信拒否リスト) のセーフリストコレクションのエントリを構成することもできます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- これらの手順を実行するには、Exchange Online PowerShell のみを使用できます。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。

- これらの手順を実行する前に、アクセス許可を割り当てる必要があります。 具体的には、**メール受信者**の役割 (既定では、**組織の管理**、**受信者の管理**、およびカスタムの**メール受信者**の役割グループに割り当てられます) または**ユーザーオプション**の役割 (既定では、**組織の管理**と**ヘルプデスク**の役割グループに割り当てられます) が必要です。 Exchange Online の役割グループにユーザーを追加するには、「 [Exchange online で役割グループを変更](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)する」を参照してください。 既定のアクセス許可を持つユーザーは、 [Exchange Online PowerShell へのアクセス](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)権を持っている限り、自分のメールボックスでこれらの手順を実行できることに注意してください。

- EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。

- 共有メールボックスの信頼できる差出人は、Azure AD に同期されず、設計に EOP れます。

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Exchange Online の PowerShell を使用してメールボックス内の迷惑メールルールを有効または無効にする

> [!NOTE]
> Outlook (Exchange キャッシュ モードで) または Web 上の Outlook で開かれているメールボックスで迷惑メール ルールを無効にするには、 **Set-MailboxJunkEmailConfiguration** コマンドレットのみを使用できます。 メールボックスが開かれていない場合は、次の`The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.`エラーが表示されます。このエラーを一括操作で抑制`-ErrorAction SlientlyContinue`する場合は、 **set-mailboxjunkemailconfiguration**コマンドに追加できます。

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

構文およびパラメーターの詳細については、「 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)」を参照してください。

> [!NOTE]
> 
> - ユーザーが自分のメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが表示されることがあります。 このエラーを一括操作で抑制するに`-ErrorAction SlientlyContinue`は、 **set-mailboxjunkemailconfiguration**コマンドにを追加します。
> 
> - 迷惑メールルールを無効にしても、Outlook の迷惑メールフィルター (構成方法によって異なります) では、メッセージがスパムであるかどうかを判断し、メッセージを自分のスパム verdict およびメールボックスのセーフリストコレクションに基づいて受信トレイまたは迷惑メールフォルダーに移動できます。 詳細については、このトピックの「[Outlook での迷惑メール設定について](#about-junk-email-settings-in-outlook)」セクションを参照してください。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

メールボックスで迷惑メール ルールを正常に有効または無効にしたことを確認するには、次のいずれかの手順を使用します。

- _ \<MailboxIdentity\> _をメールボックスの名前、エイリアス、または電子メールアドレスに置き換え、次のコマンドを実行して**Enabled**プロパティの値を確認します。

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

- _ \<MailboxIdentity\> _をメールボックスの名前、エイリアス、または電子メールアドレスに置き換え、次のコマンドを実行して迷惑メールルールの**Enabled**プロパティの値を確認します。

  ```PowerShell
  Get-InboxRule "Junk E-mail Rule" -Mailbox "<MailboxIdentity>" -IncludeHidden
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online の PowerShell を使用してメールボックスのセーフリストコレクションを構成する

メールボックスのセーフリスト コレクションには、信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リストが含まれています。 既定では、ユーザーは Outlook または web 上の Outlook の自分のメールボックスでセーフリストコレクションを構成できます。 管理者は、 **Set-MailboxJunkEmailConfiguration** コマンドレットで対応するパラメーターを使用して、ユーザーのメールボックスのセーフリスト コレクションを構成できます。 次の表に、これらのパラメーターの説明を示します。

|||
|---|---|
|**Set-mailboxjunkemailconfiguration のパラメーター**|**Outlook on the web の設定**|
|_BlockedSendersAndDomains_|**次の送信者またはドメインからのメールを [迷惑メール] フォルダーに移動する**|
|_ContactsTrusted_|**自分の連絡先からのメールを信頼する**|
|_TrustedListsOnly_|**[差出人セーフリスト] と [セーフリスト] のアドレスからの電子メールのみを信頼する**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**これらの送信者からのメールを [迷惑メール] フォルダーに移動しない**|
|

<sup>\*</sup>**メモ**:

- Exchange Online では、差出人セーフリストまたは_TrustedSendersAndDomains_パラメーターの**ドメインエントリ**は認識されないため、電子メールアドレスのみを使用します。 スタンドアロン EOP でディレクトリ同期を使用すると、ドメインエントリは既定で同期されませんが、ドメインの同期を有効にすることができます。 詳細については、「 [KB3019657](https://support.microsoft.com/help/3019657/domains-on-the-outlook-safe-senders-list-aren-t-recognized-by-exchange)」を参照してください。

- **Set-mailboxjunkemailconfiguration**コマンドレットを使用して、宛先セーフリストを直接変更することはできません ( _TrustedRecipientsAndDomains_パラメーターは機能しません)。 信頼できる差出人のリストを変更し、それらの変更が信頼できる宛先のリストに同期されます。

メールボックスにセーフリスト コレクションを構成するには、次の構文を使用します。

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

複数の値を入力して、 _BlockedSendersAndDomains_パラメーターと_TrustedSendersAndDomains_パラメーターの既存のエントリを上書きするに`"<Value1>","<Value2>"...`は、次の構文を使用します。 他の既存のエントリに影響を与えずに、1つまたは複数の値を追加または削除するには、次の構文を使用します。`@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

以下の例では、Ori Epstein のメールボックスのセーフリスト コレクションの次の設定を構成します。

- Shopping@fabrikam.com の値を受信拒否リストに追加します。

- [差出人セーフリスト] および [宛先セーフリスト] から値 chris@fourthcoffee.com を削除します。

- 信頼できる差出人として扱われるように [連絡先] フォルダー内の連絡先を構成する。

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

次の例では、組織内の全ユーザーのメールボックスの受信拒否リストから contoso.com ドメインを削除します。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

構文およびパラメーターの詳細については、「 [set-mailboxjunkemailconfiguration](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-mailboxjunkemailconfiguration)」を参照してください。

> [!NOTE]
> 
> - ユーザーが自分のメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが表示されることがあります。 このエラーを一括操作で抑制するに`-ErrorAction SlientlyContinue`は、 **set-mailboxjunkemailconfiguration**コマンドにを追加します。
> 
> - 迷惑メールルールがメールボックスで無効になっている場合でも、セーフリストコレクションを構成することができます。また、Outlook の迷惑メールフィルターは、受信トレイまたは迷惑メールフォルダーにメッセージを移動できます。 詳細については、このトピックの「[Outlook での迷惑メール設定について](#about-junk-email-settings-in-outlook)」セクションを参照してください。
> 
> - Outlook の迷惑メールフィルターには、追加のセーフリストのコレクション設定があります (たとえば、**電子メールが [差出人セーフリスト] に自動的に追加**されます)。 詳細については、「[迷惑メールフィルターを使用して表示するメッセージを制御する](https://support.office.com/article/274ae301-5db2-4aad-be21-25413cede077)」を参照してください。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

メールボックスにセーフリスト コレクションを正常に構成したことを確認するには、次のいずれかの手順を使用します。

- _ \<MailboxIdentity\> _をメールボックスの名前、エイリアス、または電子メールアドレスに置き換え、次のコマンドを実行してプロパティの値を確認します。

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  値のリストが長すぎる場合は、次の構文を使用します。

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Outlook での迷惑メール設定について

Outlook で使用できる、クライアント側の迷惑メール フィルター設定を有効にしたり、無効ににしたり、構成したりするには、グループ ポリシーを使用します。 詳細については、「 [Microsoft 365 Apps for enterprise、office 2019、および office 2016 用の管理用テンプレートファイル (ADMX/ADML) と Office カスタマイズツール](https://www.microsoft.com/download/details.aspx?id=49030)」を参照してください。

Outlook の迷惑メールフィルターで、[**ホーム** \> **迷惑** \> **メール] オプション** \>の [オート**フィルターなし** **] オプションが**既定値に設定されている場合、outlook は massages をスパムとして分類しませんが、セーフリストコレクション (差出人セーフリスト、宛先セーフリスト、受信拒否リスト) を使用して、メッセージを配信後に迷惑メールフォルダーに移動します。 これらの設定の詳細については、「[迷惑メールフィルターの概要](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)」を参照してください。

Outlook の迷惑メール フィルターが **[低]** または **[高]** に設定されている場合、Outlook の迷惑メール フィルターでは、独自の SmartScreen フィルター テクノロジを使用して、迷惑メールを識別し、[迷惑メール] フォルダーに移動します。 このスパム分類は、EOP によって決定されるスパム信頼レベル (SCL) とは別のものです。 実際には、Outlook は EOP の SCL を無視します (スパムフィルターをスキップするようにメッセージにマークされている場合を除きます)。また、そのメッセージがスパムであるかどうかを判断するために、独自の条件を使用します。 当然のことですが、スパム verdict から EOP と Outlook を同じにすることもできます。 これらの設定の詳細については、「[迷惑メールフィルターの保護レベルを変更](https://support.office.com/article/e89c12d8-9d61-4320-8c57-d982c8d52f6b)する」を参照してください。

> [!NOTE]
> 11月2016に、Microsoft は、Exchange と Outlook の SmartScreen フィルターのスパム定義の更新を中止しました。 既存の SmartScreen スパム定義は残されていましたが、その有効性は時間とともに低下する可能性があります。 詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)」 をご覧ください。

そのため、Outlook の迷惑メールフィルターは、メールボックスで迷惑メールルールが無効になっている場合でも、メールボックスのセーフリストコレクションと独自のスパム分類を使用して、メッセージを迷惑メールフォルダーに移動することができます。

Outlook と Web 上の Outlook の両方で、セーフリスト コレクションがサポートされます。 セーフリストコレクションは Exchange Online メールボックスに保存されるので、Outlook のセーフリストコレクションに対する変更は web 上の Outlook に表示され、その逆も同様です。

## <a name="limits-for-junk-email-settings"></a>迷惑メールの設定の制限

ユーザーのメールボックスに格納されているセーフリストコレクション (差出人セーフリスト、宛先セーフリスト、および受信拒否リスト) は、EOP にも同期されます。 ディレクトリ同期の場合、セーフリストコレクションは Azure AD に同期されます。

- ユーザーのメールボックスのセーフリストコレクションには、すべてのリストと、追加の迷惑メールフィルター設定を含む 510 KB の制限があります。 ユーザーがこの制限を超えると、次のような Outlook エラーが表示されます。

  > サーバーの迷惑メールリストに追加できません。 サーバーで許可されているサイズを超えています。 迷惑メールの一覧がサーバーで許可されているサイズまで縮小されるまで、サーバー上の迷惑メールフィルターは無効になります。

  この制限の詳細と変更方法については、「 [KB2669081](https://support.microsoft.com/help/2669081/outlook-error-indicates-that-you-are-over-the-junk-e-mail-list-limit)」を参照してください。

- EOP の同期されたセーフリストコレクションの同期の制限は次のとおりです。

  - [差出人セーフリスト]、[宛先セーフリスト]、および [外部連絡先からの**電子メールが信頼**されている場合、連絡先からのすべてのエントリが有効になります。1024
  - 受信拒否リストと禁止ドメインリストに含まれるエントリの合計は500です。

  1024エントリの制限に達すると、次の処理が行われます。
  
  - このリストは、PowerShell および Outlook on the web のエントリを受け付けなくなりますが、エラーは表示されません。

    Outlook ユーザーは、1024個を超えるエントリを引き続き追加することができます。これは、Outlook の制限の 510 KB に達するまでです。 EOP フィルターがメールボックスに配信される前にメッセージをブロックしない限り (メールフロールール、スプーフィング防止など)、Outlook はこれらの追加エントリを使用できます。

- ディレクトリ同期を使用すると、エントリは次の順序で Azure AD に同期されます。

  1. 連絡先**からの信頼電子メール**が有効になっている場合のメール連絡先。
  2. 差出人セーフリストと宛先セーフリストは、最初の1024エントリに対して変更が行われるたびに、組み合わせ、重複除外、およびアルファベット順に並べ替えられます。

  最初の1024エントリが使用され、関連情報がメッセージヘッダーにスタンプされます。
  
  Azure AD に同期されていない1024のエントリは、Outlook (web 上の Outlook ではない) によって処理され、メッセージヘッダーに情報はスタンプされません。

ご覧のとおり、 **[連絡先からの電子メールを信頼**する] 設定を有効にすると、同期可能な差出人と安全な受信者の数が少なくなります。 このことが問題になる場合は、グループポリシーを使用してこの機能をオフにすることをお勧めします。

- ファイル名: outlk16 ax
- ポリシー設定:**連絡先からの電子メールを信頼**する
