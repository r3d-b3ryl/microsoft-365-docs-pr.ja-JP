---
title: Exchange Online のメールボックスで迷惑メール設定を構成する
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
description: 管理者は、Exchange Online のメールボックスで迷惑メール設定を構成する方法を学習できます。 これらの設定の多くは、Outlook または Web 上の Outlook のユーザーが利用できます。
ms.openlocfilehash: 171eca8535958f01a7f749ad678e6ea9dd83d80c
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825715"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online のメールボックスで迷惑メール設定を構成する

Exchange Online にメールボックスを持つ Microsoft 365 組織では、組織のスパム対策設定が Exchange Online Protection (EOP) によって制御されます。 詳細については [、EOP のスパム対策保護を参照してください](anti-spam-protection.md)。

ただし、管理者が Exchange Online の個々のメールボックスに構成できる特定のスパム対策設定があります。

- **迷惑メールのルールを有効または無効にする**: 迷惑メールのルールは、すべてのメールボックスで既定で有効になる「迷惑メール ルール」という名前の非表示の受信トレイ ルールです。 迷惑メールのルールでは、以下の機能を制御します。

  - **スパム対策ポリシーに基づいて、メッセージを [迷惑メール] フォルダーに移動します**。スパム対策ポリシーが、スパム対策フィルター確認用の [迷惑メール] フォルダーに **アクション** を設定して構成されている場合、迷惑メール フィルター ルールは、メッセージがメールボックスに配信された後に、そのメッセージを [迷惑メール] フォルダーに移動します。 スパム対策ポリシーのスパム対策フィルターの詳細については、「EOP でスパム [対策ポリシーを構成する」を参照してください](configure-your-spam-filter-policies.md)。 同様に、ゼロア自動消去 (ZAP) が、配信されたメッセージがスパムまたはフィッシングであると判断した場合、迷惑メール フィルター ルールは、そのメッセージを [移動メッセージの迷惑メール] フォルダーに移動し **、迷惑** メール フォルダー スパム対策フィルター判定アクションに移動します。 ZAP の詳細については [、Exchange Online のゼロアハージ (ZAP) を参照してください](zero-hour-auto-purge.md)。

  - **ユーザーが Outlook または Web 上**の Outlook でユーザーに構成する迷惑メール設定: セーフリスト _コレクション_ は、信頼できる差出人のリスト、信頼できる宛先のリスト、および各メールボックスの差出人セーフ リストです。 これらのリストのエントリによって、迷惑メール ルールがメッセージを [受信トレイ] フォルダーまたは [迷惑メール] フォルダーに移動するかどうかが決定されます。 ユーザーは、Outlook または Web 上の Outlook (前の名前と呼ばられていました) に、ユーザーが独自のメールボックスのセーフリスト コレクションOutlook Web App。 管理者は、任意のユーザーのメールボックスのセーフリスト コレクションを構成できます。

メールボックスで迷惑メール ルールが有効になっている場合、EOP では、スパム フィルタリング確認の操作に基づいて、メッセージを [ **迷惑** メール] フォルダーまたはメールボックスの受信拒否リストに移動し、(メールボックスの差出人セーフ リストに基づいて) メッセージが [迷惑メール] フォルダーに配信されないようにすることができます。

 メールボックスで迷惑メール ルールが無効になっている場合、EOP では、スパム フィルタリング確認のアクションに基づいて、メッセージを [ **迷惑** メール] フォルダーまたはメールボックスのセーフリスト コレクションに移動することはできません。

管理者は、Exchange Online PowerShell を使用して、メールボックスでの迷惑メール ルールの無効化、有効化、状態の表示を行うことができます。 管理者は、Exchange Online PowerShell を使用して、メールボックスのセーフリスト コレクション ([信頼できる差出人のリスト]、[信頼できる宛先のリスト]、および [差出人を受信拒否] のリスト) にエントリを構成することもできます。

> [!NOTE]
> ユーザーが独自の信頼できる差出人のリストに追加した送信者からのメッセージは、EOP の一部として接続フィルター処理をスキップします (SCL が -1 です)。 Outlook の信頼できる差出人のリストにユーザーがエントリを追加できないようにするには、このトピックで後述する  [「Outlook](#about-junk-email-settings-in-outlook) の迷惑メール設定について」で説明するようにグループ ポリシーを使用します。 ポリシー フィルター処理では、コンテンツ フィルターと Advanced Threat Protection (ATP) のチェックが引き続きメッセージに適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- これらの手順を実行するには、Exchange Online PowerShell を使用する必要があります。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- これらの手順を実行する場合は、ああたかじ必要なアクセス許可を割り当てる必要があります。 具体的には、 **メール** 受信者の役割 (既定で **組織**管理、 **受信者**管理、 **およびカスタム メール受信者** の役割グループに割り当てられる) またはユーザー オプション ( **既定** で **組織管理]、"Help** **Desk/ヘルプ デスク" 役割グループに割** り当てられる) が必要です。 Exchange Online で役割グループにユーザーを追加するには、「Exchange Online [で役割グループを変更する」を参照してください](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups)。 既定のアクセス許可を持つユーザーは、Exchange Online PowerShell にアクセスできる場合、同じ [手順を各自分のメールボックスに対して実行できます](https://docs.microsoft.com/powershell/exchange/disable-access-to-exchange-online-powershell)。

- EOP がオンプレミスの Exchange メールボックスを保護するスタンドアロン EOP 環境では、オンプレミスの Exchange のメール フロー ルール (トランスポート ルールとも言う) を構成して、迷惑メール ルールによりメッセージが [迷惑メール] フォルダーに移動できるように、EOP スパム対策フィルター判定を解釈する必要があります。 詳細については、「[迷惑メール フォルダーにスパムを配信するようにスタンドアロン EOP を構成する](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)」を参照してください。

- 共有メールボックスの差出人セーフ リストは、Azure および ADからは、設計により同期されません。

## <a name="use-exchange-online-powershell-to-enable-or-disable-the-junk-email-rule-in-a-mailbox"></a>Exchange Online PowerShell を使用して、メールボックスで迷惑メール ルールを有効または無効にする

> [!NOTE]
> Outlook (Exchange キャッシュ モードで) または Web 上の Outlook で開かれているメールボックスで迷惑メール ルールを無効にするには、 **Set-MailboxJunkEmailConfiguration** コマンドレットのみを使用できます。 メールボックスが開かれていない場合、次のエラーが表示されます。一括操作に対して `The Junk Email configuration couldn't be set. The user needs to sign in to Outlook Web App before they can modify their Safe Senders and Recipients or Blocked Senders lists.` このエラーを表示しない場合は `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** することができます。

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
> - ユーザーがメールボックスをまだ開きなかった場合、前のコマンドを実行する際にエラーが表示される場合があります。 一括操作でこのエラーを表示しないために `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** します。
>
> - 迷惑メール ルールを無効にした場合でも、Outlook の迷惑メール フィルターは (構成方法に応じて) スパムであるかどうかを判断し、メッセージを独自のスパム判別や、メールボックスのセーフリスト コレクションに基づいて、[受信トレイ] フォルダーまたは [迷惑メール] フォルダーに移動できるかどうかを判断できます。 詳細については、このトピックの「[Outlook での迷惑メール設定について](#about-junk-email-settings-in-outlook)」セクションを参照してください。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

メールボックスで迷惑メール ルールを正常に有効または無効にしたことを確認するには、次のいずれかの手順を使用します。

- Enabled _\<MailboxIdentity\>_ プロパティの値を名前、エイリアス、または電子メール アドレスと置き換え、次の **コマンドを実行して Enabled プロパティの値を** 確認します。

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List Enabled
  ```

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell を使用してメールボックスにセーフリスト コレクションを構成する

メールボックスのセーフリスト コレクションには、信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リストが含まれています。 ユーザーは、既定では Outlook または Web 上の Outlook のユーザー独自のメールボックスのセーフリスト コレクションを構成できます。 管理者は、 **Set-MailboxJunkEmailConfiguration** コマンドレットで対応するパラメーターを使用して、ユーザーのメールボックスのセーフリスト コレクションを構成できます。 次の表に、これらのパラメーターの説明を示します。

****

|Set-MailboxJunkEmailConfiguration のパラメーター|Outlook on the web の設定|
|---|---|
|_BlockedSendersAndDomains_|**次の送信者またはドメインからのメールを [迷惑メール] フォルダーに移動する**|
|_ContactsTrusted_|**自分の連絡先からのメールを信頼する**|
|_TrustedListsOnly_|**自分の信頼できる差出人とドメインのリストおよび信頼できるメールだけを信頼できるメールのリスト**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**次の送信者からのメールは [迷惑メール] フォルダーに移動しない**|
|

<sup>\*</sup>**注**:

- Exchange Online では、 **信頼できる差出** 人のリストまたは _TrustedSendersAndDomains パラメーターのドメイン_ エントリが認識されないため、電子メール アドレスのみを使用します。 ディレクトリ同期を行うスタンドアロン EOP では、ドメイン エントリは既定では同期されませんが、ドメインの同期を有効にできます。 詳細については [、KB3019657 を参照してください](https://support.microsoft.com/help/3019657)。

- **Set-MailboxJunkEmailConfiguration**コマンドレットを使用して、信頼できる宛先のリストを直接変更することはできません _(TrustedRecipientsAndDomains_パラメーターが機能しません)。 信頼できる差出人のリストを変更し、それらの変更が信頼できる宛先のリストに同期されます。

メールボックスにセーフリスト コレクションを構成するには、次の構文を使用します。

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

複数の値を入力し _、BlockedSendersAndDomains、および TrustedSendersAndDomains_ パラメーターの既存の _エントリをすべて上書きするには_ 、次の構文を使用します `"<Value1>","<Value2>"...` 。 他の既存のエントリに影響を及ぼせずに、1 つまたは複数の値を追加または削除するには、次の構文を使用します。 `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

以下の例では、Ori Epstein のメールボックスのセーフリスト コレクションの次の設定を構成します。

- 値のリストにshopping@fabrikam.comを追加する

- 信頼できる差出chris@fourthcoffee.com信頼できるリストと信頼できる宛先のリストから削除する必要があります。

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
> - ユーザーがメールボックスをまだ開きなかった場合、前のコマンドを実行する際にエラーが表示される場合があります。 一括操作でこのエラーを表示しないために `-ErrorAction SilentlyContinue` **、Set-MailboxJunkEmailConfiguration コマンドに追加** します。
>
> - メールボックスで迷惑メールのルールが無効になっている場合でも、セーフリスト コレクションを構成できます。Outlook の迷惑メール フィルターでメッセージを [受信トレイ] または [迷惑メール] フォルダーに移動することができます。 詳細については、このトピックの「[Outlook での迷惑メール設定について](#about-junk-email-settings-in-outlook)」セクションを参照してください。
>
> - Outlook 迷惑メール フィルターには、追加のセーフリスト コレクションの設定があります (たとえば、 **差出人セーフリストにメールを自動的に追加します**)。 詳細については、「迷惑メール フィルター [を使用して、表示するメッセージを制御する」を参照してください](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

メールボックスにセーフリスト コレクションを正常に構成したことを確認するには、次のいずれかの手順を使用します。

- メールボックス _\<MailboxIdentity\>_ の名前、エイリアス、または電子メール アドレスを使用して置き換え、次のコマンドを実行してプロパティの値を確認します。

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  値のリストが長すぎる場合は、次の構文を使用します。

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Outlook での迷惑メール設定について

Outlook で使用できる、クライアント側の迷惑メール フィルター設定を有効にしたり、無効ににしたり、構成したりするには、グループ ポリシーを使用します。 詳細については [、「Microsoft 365 Apps for enterprise、Office 2019、Office 2016 用の管理用テンプレート ファイル (ADMX/ADML)」および「Office 2016 用の管理用テンプレート ファイル」および「Office 2016」](https://www.microsoft.com/download/details.aspx?id=49030) などの電子メール設定をグループ [ポリシーを使用して展開する方法を参照してください](https://support.microsoft.com/help/2252421)。

Outlook の迷惑メール フィルターが既定値 [迷惑メールの迷惑メール**Home**オプション] に [**自動**フィルターなし] に設定されている場合、Outlook では大文字と迷惑メールを分類するのを試みず、引き続きセーフリスト コレクション (信頼できる差出人のリスト、信頼できる宛先のリスト、受信拒否リスト) を使用して、配信後にメッセージを \> **Junk** \> **Junk E-Mail Options** \> **Options**[迷惑メール] フォルダーに移動しています。 これらの設定の詳細については、「迷惑メール [フィルターの概要」を参照してください](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。

Outlook の迷惑メール フィルターが **[低]** または **[高]** に設定されている場合、Outlook の迷惑メール フィルターでは、独自の SmartScreen フィルター テクノロジを使用して、迷惑メールを識別し、[迷惑メール] フォルダーに移動します。 この迷惑メールの分類は、EOP で決定される Spam Confidence Level (SCL) とは別のものです。 Outlook は、EOP から SCL を無視し (EOP がスパム フィルターをスキップするメッセージを除外した場合を除きます)、その独自の条件を使用してメッセージがスパムかどうかを判断します。 もちろん、EOP からのスパム常に詳細なディクテートが同じである可能性があります。 これらの設定の詳細については、「迷惑メール [フィルターの保護レベルを変更する」を参照してください](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。

> [!NOTE]
> 2016 年 11 月、Microsoft は Exchange と Outlook の SmartScreen フィルターのスパム定義の更新を停止しました。 既存の SmartScreen スパム定義はそのままでしたが、その効果は時間とや切り替わる可能性があります。 詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)」 をご覧ください。

したがって、メールボックスで迷惑メール ルールが無効になっている場合でも、Outlook の迷惑メール フィルターでは、メールボックスのセーフリスト コレクションと独自の迷惑メールの分類を使用して、メッセージを [迷惑メール] フォルダーに移動できます。

Outlook と Web 上の Outlook の両方で、セーフリスト コレクションがサポートされます。 セーフリスト コレクションは Exchange Online メールボックスに保存されるため、Outlook のセーフリスト コレクションに対する変更は Web 上の Outlook に表示され、その逆も同様です。

## <a name="limits-for-junk-email-settings"></a>迷惑メール設定の制限

ユーザーのメールボックスに格納されているセーフリスト コレクション (信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リスト) も EOP と同期されます。 ディレクトリ同期を使用すると、セーフリスト コレクションは Azure ユーザーの Azure AD。

- ユーザーのメールボックス内のセーフリスト コレクションのサイズは 510 KB に制限されます。すべてのリストと、他の迷惑メール フィルター設定が含まれます。 ユーザーがこの制限を超えると、次のような Outlook エラーが表示されます。

  > サーバーの迷惑メール リストに追加/アクセスできません。 サーバーで許可されているサイズを超えています。 サーバー上の迷惑メール フィルターは、迷惑メール リストがサーバーで許容されるサイズまで減らされるまで無効になります。

  この制限と変更方法の詳細については [、KB2669081 を参照してください](https://support.microsoft.com/help/2669081)。

- EOP の同期済みセーフリスト コレクションの同期に次の制限があります。

  - 信頼できる差出人のリスト、信頼できる宛先のリスト、および連絡先からのメールを信頼できる場合は、1024 エントリが合計で、信頼 **できる差出人のリスト、および外部連絡先** のエントリが合計で 1024 個。
  - 受信拒否リストおよび受信拒否ドメイン リストに登録されたエントリの合計 500

  1024 エントリの制限数に達すると、次のことが行われます。

  - リストは PowerShell および Web 上の Outlook のエントリの受け入れを停止しますが、エラーは表示されません。

    Outlook ユーザーは、Outlook の制限である 510 KB に達するまで、引き続き 1024 を超えるエントリを追加できます。 これらの追加エントリを使用できます (メール フロー ルール、スプーフィング対策など) をメールボックスに配信する前に EOP フィルターでメッセージをブロックしない場合に。

- ディレクトリ同期では、エントリが Azure サーバーに対して次AD同期されます。

  1. [連絡先からのメール **を信頼する] が有効になっている場合の** メール連絡先。
  2. 最初の 1024 エントリに対して変更が行われた場合は常に、差出人セーフ リストと信頼できる差出人のリストは、アルフォベット順に並べ替え、区切り順かれて表示されます。

  最初の 1024 エントリが使用され、関連情報はメッセージ ヘッダーにスタンプされます。

  同期されていない 1024 を超えるエントリ ADは Outlook on the web によって処理され (Outlook on the web には同期されません)、メッセージ ヘッダー内に情報はスタンプされません。

お書きのとおり、連絡先から **メールを信頼** する設定で、同期できる信頼できる差出人と信頼できる宛先の数が減少します。 これに問題が発生した場合は、グループ ポリシーを使用してこの機能を無効にしてください。

- ファイル名: outlk16.opax
- ポリシー設定: **連絡先からの電子メールを信頼する**
