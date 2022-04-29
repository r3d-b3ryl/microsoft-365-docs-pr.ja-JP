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
description: 管理者は、Exchange Online メールボックスで迷惑メール設定を構成する方法について説明します。 これらの設定の多くは、OutlookまたはOutlook on the webのユーザーが使用できます。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac7ac0f40c24c81cf916917b1b87626e032f8055
ms.sourcegitcommit: fdd0294e6cda916392ee66f5a1d2a235fb7272f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/29/2022
ms.locfileid: "65130891"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online メールボックスで迷惑メール設定を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineにメールボックスを含むMicrosoft 365組織では、組織のスパム対策設定はExchange Online Protection (EOP) によって制御されます。 詳細については、「 [EOP でのスパム対策保護](anti-spam-protection.md)」を参照してください。

ただし、管理者がExchange Onlineの個々のメールボックスに対して構成できる特定のスパム対策設定もあります。

> [!NOTE]
> EOP では、独自のメール フロー配信エージェントを使用して、迷惑メールルールを使用する代わりに、迷惑メール フォルダーにメッセージをルーティングするようになりました。 **Set-MailboxJunkEmailConfiguration** コマンドレットの _Enabled_ パラメーターは、メール フローに影響を与えなくなりました。 EOP は、スパム対策ポリシーで設定されたアクションに基づいてメッセージをルーティングします。 ユーザーのセーフ送信者リストと受信拒否リストは、引き続き通常どおりに機能します。

- **迷惑メール対策ポリシーに基づいて迷惑メール フォルダーにメッセージを移動** する: スパム フィルター判定の [迷惑 **メール フォルダーにメッセージを移動** する] アクションでスパム対策ポリシーを構成すると、メッセージがメールボックスに配信された後、迷惑メール フォルダーにメッセージが移動されます。 スパム対策ポリシーのスパム フィルターの判定の詳細については、「 [EOP でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。 同様に、0 時間の自動消去 (ZAP) によって配信されたメッセージがスパムまたはフィッシングであると判断された場合、メッセージは迷惑メール フォルダーに移動して迷惑 **メール フォルダー** のスパム フィルターの判定アクションに移動されます。 ZAP の詳細については、[Exchange Onlineのゼロ時間自動消去 (ZAP) に関するページを](zero-hour-auto-purge.md)参照してください。

- **OutlookまたはOutlook on the webでユーザーが自分で構成する迷惑メール設定**: _セーフリスト コレクション_ は、セーフ送信者の一覧、セーフ受信者の一覧、および各メールボックスの受信拒否リストです。 これらの一覧のエントリによって、メッセージが受信トレイまたは迷惑メール フォルダーに移動されるかどうかが決まります。 ユーザーは、OutlookまたはOutlook on the web (以前はOutlook Web Appと呼ばれて) 内の自分のメールボックスのセーフリスト コレクションを構成できます。 管理者は、任意のユーザーのメールボックスでセーフリスト コレクションを構成できます。

EOP では、迷惑メール フィルターの判定アクション[メッセージを迷惑メール フォルダーまたはメールボックスのブロックされた送信者の一覧に移動する] に基づいて迷惑 **メール フォルダーにメッセージを移動** し、メッセージが迷惑メール フォルダーに配信されないようにすることができます (メールボックスのセーフ送信者の一覧に基づく)。

管理者は、Exchange Online PowerShell を使用して、メールボックスのセーフリスト コレクション (セーフ差出人リスト、セーフ受信者一覧、および受信拒否リスト) のエントリを構成できます。

> [!NOTE]
> ユーザーが自分のセーフ送信者リストに追加した送信者からのメッセージは、EOP の一部としてコンテンツ フィルター処理をスキップします (SCL は -1)。 ユーザーがOutlookで自分のセーフ送信者リストにエントリを追加できないようにするには、この記事の後半の「Outlookの[迷惑メール設定について](#about-junk-email-settings-in-outlook)」セクションで説明されているようにグループ ポリシーを使用します。 ポリシー フィルター処理、コンテンツ フィルター処理、Defender for Office 365 チェックは、引き続きメッセージに適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- PowerShell Exchange Onlineのみを使用して、この記事の手順を実行できます。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行するには、Exchange Onlineでアクセス許可を割り当てる必要があります。 具体的には、 **メール受信者** ロール ( **組織の管理**、 **受信者管理**、および **カスタム メール受信者** の役割グループに既定で割り当てられている) または **ユーザー オプション** ロール (既定で **組織の管理** と **ヘルプ デスク** の役割グループに割り当てられている) が必要です。 Exchange Onlineのロール グループにユーザーを追加するには、「[Exchange Onlineの役割グループを変更する](/Exchange/permissions-exo/role-groups#modify-role-groups)」を参照してください。 既定のアクセス許可を持つユーザーは、[PowerShell にアクセス](/powershell/exchange/disable-access-to-exchange-online-powershell)できる限り、自分のメールボックスで同じ手順Exchange Online実行できることに注意してください。

- EOP がオンプレミスの Exchange メールボックスを保護するハイブリット環境では、オンプレミスの Exchange でメール フロー ルール (トランスポート ルールとも言う) を構成する必要があります。これらのメール フロー ルールは、メールボックス内の迷惑メール ルールがメッセージを[迷惑メール] フォルダーに移動できるように、EOP スパム フィルター判定を解釈します。詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。

- 共有メールボックスのセーフ送信者は、設計上Azure ADおよび EOP に同期されません。

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell を使用してメールボックスのセーフリスト コレクションを構成する

メールボックスのセーフリスト コレクションには、信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リストが含まれています。 既定では、ユーザーはOutlookまたはOutlook on the web内の自分のメールボックスでセーフリスト コレクションを構成できます。 管理者は、 **Set-MailboxJunkEmailConfiguration** コマンドレットで対応するパラメーターを使用して、ユーザーのメールボックスのセーフリスト コレクションを構成できます。 次の表に、これらのパラメーターの説明を示します。

|Set-MailboxJunkEmailConfigurationのパラメーター|Outlook on the web設定|
|---|---|
|_BlockedSendersAndDomains_|**次の送信者またはドメインからのメールを [迷惑メール] フォルダーに移動する**|
|_ContactsTrusted_|**自分の連絡先からのメールを信頼する**|
|_TrustedListsOnly_|**自分のセーフ送信者とドメインの一覧とセーフメーリング リスト内のアドレスからのメールのみを信頼する**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**これらの送信者から迷惑メール フォルダーにメールを移動しない**|

<sup>\*</sup>**注**:

- Exchange Onlineでは、セーフ Senders リストまたは _TrustedSendersAndDomains_ パラメーターの **ドメイン エントリ** は認識されないため、電子メール アドレスのみを使用します。 ディレクトリ同期を使用するスタンドアロン EOP では、ドメイン エントリは既定では同期されませんが、ドメインの同期を有効にできます。 詳細については、 [KB3019657 を](https://support.microsoft.com/help/3019657)参照してください。
- **Set-MailboxJunkEmailConfiguration** コマンドレットを使用して、セーフ受信者の一覧を直接変更することはできません (_TrustedRecipientsAndDomains_ パラメーターは機能しません)。 信頼できる差出人のリストを変更し、それらの変更が信頼できる宛先のリストに同期されます。

メールボックスにセーフリスト コレクションを構成するには、次の構文を使用します。

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

複数の値を入力し、 _BlockedSendersAndDomains_ および _TrustedSendersAndDomains_ パラメーターの既存のエントリを上書きするには、次の構文 `"<Value1>","<Value2>"...`を使用します。 他の既存のエントリに影響を与えずに 1 つ以上の値を追加または削除するには、次の構文を使用します。 `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

以下の例では、Ori Epstein のメールボックスのセーフリスト コレクションの次の設定を構成します。

- ブロックされた送信者の一覧に shopping@fabrikam.com 値を追加します。
- セーフ送信者の一覧とセーフ受信者の一覧から chris@fourthcoffee.com 値を削除します。
- 信頼できる差出人として扱われるように [連絡先] フォルダー内の連絡先を構成する。

```PowerShell
Set-MailboxJunkEmailConfiguration "Ori Epstein" -BlockedSendersAndDomains @{Add="shopping@fabrikam.com"} -TrustedSendersAndDomains @{Remove="chris@fourthcoffee.com"} -ContactsTrusted $true
```

次の例では、組織内の全ユーザーのメールボックスの受信拒否リストから contoso.com ドメインを削除します。

```PowerShell
$All = Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited; $All | foreach {Set-MailboxJunkEmailConfiguration $_.Name -BlockedSendersAndDomains @{Remove="contoso.com"}}
```

構文とパラメーターの詳細については、「 [Set-MailboxJunkEmailConfiguration」を](/powershell/module/exchange/set-mailboxjunkemailconfiguration)参照してください。

> [!NOTE]
>
> - ユーザーが自分のメールボックスを開いたことがない場合は、前のコマンドを実行するとエラーが表示されることがあります。 一括操作でこのエラーを抑制するには、**Set-MailboxJunkEmailConfiguration** コマンドに追加`-ErrorAction SilentlyContinue`します。
> - Outlook迷惑メール フィルターには、セーフリストコレクションの設定が追加されています (たとえば、[送信者 **のセーフ一覧にメールを送信するユーザーを自動的に追加** します)。 詳細については、「 [迷惑メール フィルターを使用して、表示されるメッセージを制御する」を参照してください](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

メールボックスにセーフリスト コレクションを正常に構成したことを確認するには、次のいずれかの手順を使用します。

- メールボックスの名前、エイリアス、または電子メール アドレスに置き換え _\<MailboxIdentity\>_ 、次のコマンドを実行してプロパティ値を確認します。

  ```PowerShell
  Get-MailboxJunkEmailConfiguration -Identity "<MailboxIdentity>" | Format-List trusted*,contacts*,blocked*
  ```

  値の一覧が長すぎる場合は、次の構文を使用します。

  ```PowerShell
  (Get-MailboxJunkEmailConfiguration -Identity <MailboxIdentity>).BlockedSendersAndDomains
  ```

## <a name="about-junk-email-settings-in-outlook"></a>Outlook での迷惑メール設定について

Outlook で使用できる、クライアント側の迷惑メール フィルター設定を有効にしたり、無効ににしたり、構成したりするには、グループ ポリシーを使用します。 詳細については、「Microsoft 365 Apps for enterprise、[Office 2019、Office 2016 用の管理用テンプレート ファイル (ADMX/ADML) とOfficeカスタマイズ ツール](https://www.microsoft.com/download/details.aspx?id=49030)」および「グループ ポリシー[を使用して迷惑メール設定 (セーフ送信者リストなど) を展開する方法」を参照してください。](https://support.microsoft.com/help/2252421).

Outlook迷惑メール フィルターが既定値に設定されている場合、[**ホーム** \> **迷惑** \> **メールメール オプション オプション**\>] で **[自動フィルターなし**] に設定されている場合、Outlookメッセージをスパムとして分類しようとはしませんが、セーフリスト コレクション ([セーフ差出人の一覧] セーフ 受信者の一覧と受信拒否リスト) を使用して、配信後に迷惑メール フォルダーにメッセージを移動します。 これらの設定の詳細については、「 [迷惑メール フィルターの概要](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)」を参照してください。

> [!NOTE]
> Microsoft 365組織では、迷惑メール フィルターを [自動フィルターなし] に設定Outlook、EOP からのスパム **フィルター** の判定で不要な競合 (正と負の両方) を防ぐことをお勧めします。

Outlook の迷惑メール フィルターが **[低]** または **[高]** に設定されている場合、Outlook の迷惑メール フィルターでは、独自の SmartScreen フィルター テクノロジを使用して、迷惑メールを識別し、[迷惑メール] フォルダーに移動します。 このスパム分類は、EOP によって決定されるスパム信頼レベル (SCL) とは別です。 実際、Outlookは EOP からの SCL を無視し (EOP がスパム フィルターをスキップするようにメッセージをマークした場合を除く)、独自の条件を使用してメッセージがスパムであるかどうかを判断します。 もちろん、EOP とOutlookからのスパムの判定が同じである可能性があります。 これらの設定の詳細については、「 [迷惑メール フィルターで保護レベルを変更する」を](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)参照してください。

> [!NOTE]
> 2016 年 11 月、Microsoft は、ExchangeおよびOutlookの SmartScreen フィルターのスパム定義更新プログラムの生成を停止しました。 既存の SmartScreen スパム定義は残されていましたが、その有効性は時間の経過と共に低下する可能性があります。 詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)」 をご覧ください。

そのため、Outlook迷惑メール フィルターは、メールボックスのセーフリスト コレクションと独自のスパム分類を使用して、迷惑メール フォルダーにメッセージを移動できます。

Outlook と Web 上の Outlook の両方で、セーフリスト コレクションがサポートされます。 セーフリスト コレクションはExchange Online メールボックスに保存されるため、Outlookのセーフリスト コレクションへの変更はOutlook on the webに表示され、その逆も同様です。

## <a name="limits-for-junk-email-settings"></a>迷惑メール設定の制限

ユーザーのメールボックスに格納されているセーフリスト コレクション (セーフ送信者の一覧、セーフ受信者の一覧、および受信拒否リスト) も EOP に同期されます。 ディレクトリ同期では、セーフリスト コレクションはAzure ADに同期されます。

- ユーザーのメールボックス内のセーフリスト コレクションには、すべてのリストと追加の迷惑メール フィルター設定を含む 510 KB の制限があります。 ユーザーがこの制限を超えると、次のようなOutlookエラーが表示されます。

  > サーバーの迷惑メール リストに追加できない/できない。 サーバーで許可されているサイズを超えています。 迷惑メール リストがサーバーで許可されているサイズに縮小されるまで、サーバー上の迷惑メール フィルターは無効になります。

  この制限とその変更方法の詳細については、 [KB2669081](https://support.microsoft.com/help/2669081) を参照してください。

- EOP の同期セーフリスト コレクションには、次の同期制限があります。
  - 連絡先 **からの電子メールを信頼** するが有効になっている場合は、セーフ送信者の一覧、セーフ受信者の一覧、および外部連絡先の合計 1024 エントリ。
  - [ブロックされた送信者] リストと [ブロックされたドメイン] リストの合計エントリ数は 500 個です。

  1024 エントリの制限に達すると、次のことが発生します。

  - リストは PowerShell とOutlook on the webのエントリの受け入れを停止しますが、エラーは表示されません。

    Outlookユーザーは、510 KB のOutlook制限に達するまで、1024 を超えるエントリを追加し続けることができます。 EOP フィルターがメールボックスへの配信前にメッセージをブロックしない限り、これらの追加のエントリを使用できるOutlook (メール フロー ルール、スプーフィング対策など)。

- ディレクトリ同期では、エントリは次の順序でAzure ADに同期されます。
  1. 連絡先からの信頼メールが有効になっている場合 **は、連絡先にメールを送信します** 。
  2. セーフ送信者リストとセーフ受信者リストは、最初の 1024 エントリに対して変更が行われるたびに、結合、重複解除、並べ替えがアルファベット順に行われます。

  最初の 1024 エントリが使用され、関連情報がメッセージ ヘッダーにスタンプされます。

  Azure ADに同期されなかった 1024 を超えるエントリはOutlook (Outlook on the webではなく) によって処理され、メッセージ ヘッダーに情報はスタンプされません。

ご覧のように、[**連絡先からのメールを信頼** する] 設定を有効にすると、同期できるセーフ送信者とセーフ受信者の数が減ります。 これが懸念される場合は、グループ ポリシーを使用してこの機能をオフにすることをお勧めします。

- ファイル名: outlk16.opax
- ポリシー設定: **連絡先からの電子メールを信頼する**
