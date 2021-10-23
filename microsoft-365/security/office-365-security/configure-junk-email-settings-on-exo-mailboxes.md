---
title: Exchange Online メールボックスで迷惑メール設定を構成する
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MOE150
- MED150
- MBS150
- MET150
ms.collection:
- M365-security-compliance
description: 管理者は、ユーザーのメールボックスで迷惑メール設定を構成するExchange Onlineできます。 これらの設定の多くは、OutlookまたはOutlook on the web。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d3a55b1f49430d3c2a61b0db44e3ce8f8a060093
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555490"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online メールボックスで迷惑メール設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

組織Microsoft 365メールボックスが含Exchange Online組織のスパム対策設定は、組織のスパム対策 (EOP) Exchange Online Protection制御されます。 詳細については [、「EOP でのスパム対策保護」を参照してください](anti-spam-protection.md)。

ただし、管理者がユーザーの個々のメールボックスで構成できる特定のスパム対策設定Exchange Online。

> [!NOTE]
> EOP は、独自のメール フロー配信エージェントを使用して、迷惑メール ルールを使用する代わりに、迷惑メール フォルダーにメッセージをルーティングします。 **Set-MailboxJunkEmailConfiguration** コマンドレットの Enabled パラメーターは、メール フローに影響を与えなくなりました。  EOP は、スパム対策ポリシーで設定されたアクションに基づいてメッセージをルーティングします。 ユーザーの [送信者] セーフリストと [受信拒否] リストは、通常どおり動作します。

- **スパム対策** ポリシーに基づいてメッセージを迷惑メール フォルダーに移動する : スパム対策ポリシーが [スパムフィルターの評決の迷惑メール フォルダーにメッセージを移動する] アクションで構成されている場合、メッセージはメールボックスに配信された後に迷惑メール フォルダーに移動されます。 スパム対策ポリシーのスパム フィルターの評決の詳細については、「EOP でスパム対策ポリシーを構成する」 [を参照してください](configure-your-spam-filter-policies.md)。 同様に、0 時間自動削除 (ZAP) によって配信されたメッセージがスパムまたはフィッシングと判断された場合、メッセージは迷惑メールフォルダースパム フィルターの評決アクションにメッセージを移動する迷惑メール フォルダーに移動されます。 ZAP の詳細については、「ゼロ時間自動削除[(ZAP)」を参照Exchange Online。](zero-hour-auto-purge.md)

- **Outlook** または Outlook on the web でユーザーが自分で構成する迷惑メール設定 :セーフリスト コレクションは、セーフ Senders リスト、セーフ Recipients リスト、および各メールボックスの [送信者のブロック] リストです。 これらのリスト内のエントリによって、メッセージが受信トレイまたは迷惑メール フォルダーに移動されるかどうかが決定されます。 ユーザーは、自分のメールボックスのセーフリスト コレクションを Outlookまたは Outlook on the web (以前は Outlook Web App) で構成できます。 管理者は、任意のユーザーのメールボックスでセーフリスト コレクションを構成できます。

EOP は、スパム フィルターの評決アクションに基づいてメッセージを迷惑メール フォルダーに移動できます。メッセージを迷惑メール フォルダーまたはメールボックスの [受信拒否] リストに移動し、(メールボックスの セーフ Senders リストに基づいて) 迷惑メール フォルダーにメッセージが配信されるのを防ぐ。

管理者は Exchange Online PowerShell を使用して、メールボックスのセーフリスト コレクション内のエントリ (セーフ Senders リスト、セーフ 受信者リスト、および受信拒否リスト) を構成できます。

> [!NOTE]
> ユーザーが自分の送信者リストに追加した送信者からのメッセージセーフ送信者リストは、EOP の一部としてコンテンツ フィルター処理をスキップします (SCL は -1)。 ユーザーが Outlook の セーフ Senders リストにエントリを追加し込むのを防ぐには、この記事の後半の[「Outlook](#about-junk-email-settings-in-outlook)の迷惑メール設定について」に記載されているグループ ポリシーを使用します。 ポリシー フィルター、コンテンツ フィルター、および Defender Office 365チェックは引き続きメッセージに適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報

- この記事の手順を実行Exchange Online PowerShell を使用できるのは、PowerShell のみです。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行するには、Exchange Onlineにアクセス許可を割り当てる必要があります。 具体的には、メール受信者の役割 (既定では[組織の管理]、[受信者の管理]、および [カスタム メール受信者] 役割グループに割り当てられている)、または [ユーザーオプション] 役割 (既定では [組織の管理] 役割グループと [ヘルプ デスク] 役割グループに割り当てられている) が必要です。     ユーザーをグループ内の役割グループに追加するにはExchange Onlineで役割グループを変更[するを参照Exchange Online。](/Exchange/permissions-exo/role-groups#modify-role-groups) 既定のアクセス許可を持つユーザーは、PowerShell にアクセスできる限り、自分のメールボックスでこれらの同じ[手順Exchange Online注意してください](/powershell/exchange/disable-access-to-exchange-online-powershell)。

- EOP がオンプレミスの Exchange メールボックスを保護するハイブリッド環境では、オンプレミスのメールボックスでメール フロー ルール (トランスポート ルールとも呼ばれる) を構成する必要Exchange。 これらのメール フロー ルールは、EOP スパム フィルターの評決を変換し、メールボックス内の迷惑メール ルールがメッセージを迷惑メール フォルダーに移動できます。 詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。

- セーフメールボックスの送信者は、設計上、Azure AD EOP と同期されません。

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>PowerShell Exchange Onlineを使用してメールボックスのセーフリスト コレクションを構成する

メールボックスのセーフリスト コレクションには、信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リストが含まれています。 既定では、ユーザーは自分のメールボックスでセーフリスト コレクションを構成し、OutlookまたはOutlook on the web。 管理者は、 **Set-MailboxJunkEmailConfiguration** コマンドレットで対応するパラメーターを使用して、ユーザーのメールボックスのセーフリスト コレクションを構成できます。 次の表に、これらのパラメーターの説明を示します。

<br>

****

|パラメーター on Set-MailboxJunkEmailConfiguration|Outlook on the web設定|
|---|---|
|_BlockedSendersAndDomains_|**次の送信者またはドメインからのメールを [迷惑メール] フォルダーに移動する**|
|_ContactsTrusted_|**自分の連絡先からのメールを信頼する**|
|_TrustedListsOnly_|**自分の送信者とドメインリストおよびセーフリスト内のアドレスからのセーフ信頼する**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**これらの送信者から迷惑メール フォルダーにメールを移動しない**|
|

<sup>\*</sup>**注**:

- このExchange Online、セーフ Senders リストまたは _TrustedSendersAndDomains_ パラメーターのドメイン エントリは認識されないので、電子メール アドレスのみを使用します。  ディレクトリ同期を使用するスタンドアロン EOP では、ドメイン エントリは既定では同期されませんが、ドメインの同期を有効にできます。 詳細については [、「KB3019657」を参照してください](https://support.microsoft.com/help/3019657)。
- **Set-MailboxJunkEmailConfiguration** コマンドレット _(TrustedRecipientsAndDomains_ パラメーターが機能しない) を使用して、セーフ 受信者リストを直接変更することはできません。 信頼できる差出人のリストを変更し、それらの変更が信頼できる宛先のリストに同期されます。

メールボックスにセーフリスト コレクションを構成するには、次の構文を使用します。

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

複数の値を入力し _、BlockedSendersAndDomains_ および _TrustedSendersAndDomains_ パラメーターの既存のエントリを上書きするには、次の構文を使用します `"<Value1>","<Value2>"...` 。 他の既存のエントリに影響を与えることなく 1 つ以上の値を追加または削除するには、次の構文を使用します。 `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

以下の例では、Ori Epstein のメールボックスのセーフリスト コレクションの次の設定を構成します。

- [受信拒否] shopping@fabrikam.com に値を追加します。
- [送信者] リスト chris@fourthcoffee.com [受信者] セーフリストから、セーフを削除します。
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
> - 迷惑Outlookメール フィルターには、セーフリスト コレクションの設定が追加されています (たとえば、電子メールのユーザーを [送信者] リストに自動的セーフ **追加します**)。 詳細については、「迷惑メール フィルター [を使用して表示されるメッセージを制御する」を参照してください](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)。

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

Outlook で使用できる、クライアント側の迷惑メール フィルター設定を有効にしたり、無効ににしたり、構成したりするには、グループ ポリシーを使用します。 詳細については、「管理用テンプレート ファイル[(ADMX/ADML)、Office カスタマイズ ツール for Microsoft 365 Apps for enterprise、Office 2019、Office 2016」](https://www.microsoft.com/download/details.aspx?id=49030)および「グループ ポリシーを使用して セーフ[送信者](https://support.microsoft.com/help/2252421)リストなどの迷惑メール設定を展開する方法」を参照してください。

Outlook 迷惑メール フィルターが既定値に設定されている場合[ホーム迷惑メール 電子メール オプション オプション] で自動フィルター処理を行わない場合、Outlook はメッセージをスパムとして分類しようとはしませんが、セーフリスト コレクション \>  \>  \> (セーフ Senders リスト、セーフ 受信者リスト、および受信拒否リスト) を使用してメッセージを迷惑メール f に移動します。配信後に古い。 これらの設定の詳細については、「迷惑メール [フィルターの概要」を参照してください](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)。

Outlook の迷惑メール フィルターが **[低]** または **[高]** に設定されている場合、Outlook の迷惑メール フィルターでは、独自の SmartScreen フィルター テクノロジを使用して、迷惑メールを識別し、[迷惑メール] フォルダーに移動します。 このスパム分類は、EOP によって決定されるスパム信頼レベル (SCL) とは別です。 実際、Outlook EOP からの SCL を無視し (EOP がスパム フィルター処理をスキップするようにメッセージをマークしない限り)、独自の条件を使用してメッセージがスパムであるかどうかを判断します。 もちろん、EOP とメールからのスパムのOutlook同じ可能性があります。 これらの設定の詳細については、「迷惑メール フィルター [で保護レベルを変更する」を参照してください](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)。

> [!NOTE]
> 2016 年 11 月、Microsoft は SmartScreen フィルターのスパム定義更新プログラムの作成を停止ExchangeおよびOutlook。 既存の SmartScreen スパム定義は残されたが、その有効性は時間の流れる間に低下する可能性が高い。 詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)」 をご覧ください。

そのため、Outlook迷惑メール フィルターは、メールボックスのセーフリスト コレクションと独自のスパム分類を使用して、メッセージを迷惑メール フォルダーに移動できます。

Outlook と Web 上の Outlook の両方で、セーフリスト コレクションがサポートされます。 セーフリスト コレクションは Exchange Online メールボックスに保存され、Outlook のセーフリスト コレクションへの変更は Outlook on the webに表示され、その逆も同様です。

## <a name="limits-for-junk-email-settings"></a>迷惑メール設定の制限

ユーザーのメールボックスに格納されているセーフリスト コレクション (セーフ Senders リスト、セーフ 受信者リスト、および受信拒否リスト) も EOP に同期されます。 ディレクトリ同期を使用すると、セーフリスト コレクションが同期され、Azure AD。

- ユーザーのメールボックス内のセーフリスト コレクションの制限は 510 KB で、これにはすべてのリストと追加の迷惑メール フィルター設定が含まれます。 ユーザーがこの制限を超えると、次のようなOutlookエラーが表示されます。

  > サーバーの迷惑メール リストに追加できない/追加できません。 サーバーで許可されているサイズを超えました。 サーバー上の迷惑メール フィルターは、迷惑メール リストがサーバーで許可されるサイズに縮小されるまで無効になります。

  この制限と変更方法の詳細については [、「KB2669081」を参照してください](https://support.microsoft.com/help/2669081)。

- EOP の同期セーフリスト コレクションには、次の同期制限があります。
  - 連絡先からの信頼メールが有効になっている場合、セーフ 送信者リスト、セーフ 受信者リスト、外部連絡先の合計エントリ数は 1024 件です。 
  - [ブロックされた送信者] リストと [ブロックされたドメイン] リストの合計エントリ数は 500 です。

  1024 エントリの制限に達すると、次のことが発生します。

  - 一覧は PowerShell のエントリの受け入Outlook on the web停止しますが、エラーは表示されません。

    Outlookユーザーは、510 KB の上限に達するまで、1024 Outlookを追加できます。 Outlook、EOP フィルターがメールボックスに配信する前にメッセージをブロックしない限り、これらの追加エントリを使用できます (メール フロー ルール、スプーフィング防止など)。

- ディレクトリ同期では、エントリは次の順序Azure AD同期されます。
  1. 連絡先からのメールの **信頼が有効になっている場合は、連絡先に** メールを送信します。
  2. 最初セーフ 1024 エントリに対して変更が行われた場合、セーフ 送信者リストと セーフ 受信者リストは、アルファベット順に結合、重複、および並べ替えされます。

  最初の 1024 エントリが使用され、関連する情報がメッセージ ヘッダーにスタンプされます。

  Azure AD に同期されていない 1024 を超えるエントリは Outlook (Outlook on the web ではない) によって処理され、メッセージ ヘッダーには情報がスタンプされません。

ご覧のように、[連絡先からのメールの信頼] 設定を有効にすると、同期できる送信者と受信者セーフの数セーフ減らされます。 これが懸念される場合は、グループ ポリシーを使用してこの機能をオフにすることをお勧めします。

- ファイル名: outlk16.opax
- ポリシー設定: **連絡先からの電子メールを信頼する**
