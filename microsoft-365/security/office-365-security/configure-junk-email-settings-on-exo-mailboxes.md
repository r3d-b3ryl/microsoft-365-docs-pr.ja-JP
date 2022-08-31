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
description: 管理者は、Exchange Online メールボックスで迷惑メール設定を構成する方法について説明します。 これらの設定の多くは、Outlook またはOutlook on the webのユーザーが使用できます。
ms.subservice: mdo
ms.service: microsoft-365-security
ms.openlocfilehash: 9f8c5ed64526b03cb4a47b06962be94274517789
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67483478"
---
# <a name="configure-junk-email-settings-on-exchange-online-mailboxes"></a>Exchange Online メールボックスで迷惑メール設定を構成する

[!INCLUDE [MDO Trial banner](../includes/mdo-trial-banner.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Exchange Onlineにメールボックスを含む Microsoft 365 組織では、組織のスパム対策設定はExchange Online Protection (EOP) によって制御されます。 詳細については、「 [EOP でのスパム対策保護](anti-spam-protection.md)」を参照してください。

ただし、管理者がExchange Onlineの個々のメールボックスに対して構成できる特定のスパム対策設定もあります。

> [!NOTE]
> EOP では、独自のメール フロー配信エージェントを使用して、迷惑メール ルールを使用する代わりに、メッセージを迷惑メール Email フォルダーにルーティングするようになりました。 **Set-MailboxJunkEmailConfiguration** コマンドレットの _Enabled_ パラメーターは、メール フローに影響を与えなくなりました。 EOP は、スパム対策ポリシーで設定されたアクションに基づいてメッセージをルーティングします。 ユーザーの差出人セーフ リストと受信拒否リストは、引き続き通常どおりに機能します。

- スパム **対策ポリシーに基づいて迷惑メール Email フォルダーにメッセージを移動** する: スパム フィルターの判定に対してメッセージを **迷惑メール Email フォルダーに移動** するアクションでスパム対策ポリシーを構成すると、メッセージはメールボックスに配信された後、迷惑メール Email フォルダーに移動されます。 スパム対策ポリシーのスパム フィルターの判定の詳細については、「 [EOP でスパム対策ポリシーを構成](configure-your-spam-filter-policies.md)する」を参照してください。 同様に、0 時間の自動消去 (ZAP) で配信されたメッセージがスパムまたはフィッシングであると判断した場合、メッセージは迷惑メール Email フォルダーに移動され、**メッセージを迷惑メール Email フォルダーに移動** して、判定アクションをフィルター処理します。 ZAP の詳細については、[Exchange Onlineのゼロ時間自動消去 (ZAP) に関するページを](zero-hour-auto-purge.md)参照してください。

- **Outlook またはOutlook on the webでユーザーが自分で構成する迷惑メール設定**: _セーフリスト コレクション_ は、各メールボックスの[差出人セーフ リスト]、[差出人セーフ リスト]、および [受信拒否リスト] の一覧です。 これらの一覧のエントリによって、メッセージが受信トレイまたは迷惑メール Email フォルダーに移動されるかどうかが決まります。 ユーザーは、Outlook または Outlook on the web で自分のメールボックスのセーフリスト コレクションを構成できます (以前は Outlook Web App と呼ばれていました)。 管理者は、任意のユーザーのメールボックスでセーフリスト コレクションを構成できます。

EOP は、迷惑メール フィルターの判定アクション [メッセージを迷惑メール Email フォルダーまたはメールボックスのブロックされた送信者の一覧に移動する] に基づいて迷惑メール **Email フォルダー** にメッセージを移動し、メッセージが迷惑メール Email フォルダーに配信されないようにすることができます (メールボックスの [差出人セーフ リストに基づく)] です。

管理者は、Exchange Online PowerShell を使用して、メールボックスのセーフリスト コレクション ([差出人セーフ リスト]、[差出人セーフ リスト]、および [受信拒否リスト] リスト) のエントリを構成できます。

> [!NOTE]
> ユーザーが自分の差出人セーフ リストに追加した送信者からのメッセージは、EOP の一部としてコンテンツ フィルター処理をスキップします (SCL は -1 です)。 ユーザーが Outlook の [差出人セーフ リスト] にエントリを追加できないようにするには、この記事の後半の「Outlook の[迷惑メール設定について](#about-junk-email-settings-in-outlook)」セクションで説明されているように、グループ ポリシーを使用します。 ポリシー フィルター処理、コンテンツ フィルター処理、Defender for Office 365 チェックは、引き続きメッセージに適用されます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- PowerShell Exchange Onlineのみを使用して、この記事の手順を実行できます。 Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行するには、Exchange Onlineでアクセス許可を割り当てる必要があります。 具体的には、 **メール受信者** ロール ( **組織の管理**、 **受信者管理**、および **カスタム メール受信者** の役割グループに既定で割り当てられている) または **ユーザー オプション** ロール (既定で **組織の管理** と **ヘルプ デスク** の役割グループに割り当てられている) が必要です。 Exchange Onlineのロール グループにユーザーを追加するには、「[Exchange Onlineの役割グループを変更する](/Exchange/permissions-exo/role-groups#modify-role-groups)」を参照してください。 既定のアクセス許可を持つユーザーは、[PowerShell にアクセス](/powershell/exchange/disable-access-to-exchange-online-powershell)できる限り、自分のメールボックスで同じ手順Exchange Online実行できることに注意してください。

- EOP がオンプレミスの Exchange メールボックスを保護するハイブリット環境では、オンプレミスの Exchange でメール フロー ルール (トランスポート ルールとも言う) を構成する必要があります。これらのメール フロー ルールは、メールボックス内の迷惑メール ルールがメッセージを[迷惑メール] フォルダーに移動できるように、EOP スパム フィルター判定を解釈します。詳細については、「[迷惑メール フォルダーにスパムを配信するように EOP を構成する](/exchange/standalone-eop/configure-eop-spam-protection-hybrid)」を参照してください。

- 共有メールボックスのセーフ センダーは、設計上 Azure AD および EOP に同期されません。

## <a name="use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox"></a>Exchange Online PowerShell を使用してメールボックスのセーフリスト コレクションを構成する

メールボックスのセーフリスト コレクションには、信頼できる差出人のリスト、信頼できる宛先のリスト、および受信拒否リストが含まれています。 既定では、ユーザーは Outlook またはOutlook on the webで自分のメールボックスでセーフリスト コレクションを構成できます。 管理者は、 **Set-MailboxJunkEmailConfiguration** コマンドレットで対応するパラメーターを使用して、ユーザーのメールボックスのセーフリスト コレクションを構成できます。 次の表に、これらのパラメーターの説明を示します。

|Set-MailboxJunkEmailConfigurationのパラメーター|Outlook on the web設定|
|---|---|
|_BlockedSendersAndDomains_|**次の送信者またはドメインからのメールを [迷惑メール] フォルダーに移動する**|
|_ContactsTrusted_|**自分の連絡先からのメールを信頼する**|
|_TrustedListsOnly_|**自分の差出人セーフ リストとドメイン リストと安全なメーリング リスト内のアドレスからのメールのみを信頼する**|
|_TrustedSendersAndDomains_<sup>\*</sup>|**これらの送信者から迷惑メール フォルダーにメールを移動Emailしない**|

<sup>\*</sup>**注**:

- Exchange Onlineでは、差出人セーフ リストまたは _TrustedSendersAndDomains_ パラメーターの **ドメイン エントリ** は認識されないため、電子メール アドレスのみを使用します。 ディレクトリ同期を使用するスタンドアロン EOP では、ドメイン エントリは既定では同期されませんが、ドメインの同期を有効にできます。 詳細については、 [KB3019657 を](https://support.microsoft.com/help/3019657)参照してください。
- **Set-MailboxJunkEmailConfiguration** コマンドレットを使用して安全な受信者の一覧を直接変更することはできません (_TrustedRecipientsAndDomains_ パラメーターは機能しません)。 信頼できる差出人のリストを変更し、それらの変更が信頼できる宛先のリストに同期されます。

メールボックスにセーフリスト コレクションを構成するには、次の構文を使用します。

```PowerShell
Set-MailboxJunkEmailConfiguration <MailboxIdentity> -BlockedSendersAndDomains <EmailAddressesOrDomains | $null> -ContactsTrusted <$true | $false> -TrustedListsOnly <$true | $false> -TrustedSendersAndDomains  <EmailAddresses | $null>
```

複数の値を入力し、 _BlockedSendersAndDomains_ および _TrustedSendersAndDomains_ パラメーターの既存のエントリを上書きするには、次の構文 `"<Value1>","<Value2>"...`を使用します。 他の既存のエントリに影響を与えずに 1 つ以上の値を追加または削除するには、次の構文を使用します。 `@{Add="<Value1>","<Value2>"... ; Remove="<Value3>","<Value4>...}`

以下の例では、Ori Epstein のメールボックスのセーフリスト コレクションの次の設定を構成します。

- ブロックされた送信者の一覧に shopping@fabrikam.com 値を追加します。
- [差出人セーフ リスト] と [差出人セーフ リスト] から chris@fourthcoffee.com 値を削除します。
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
> - Outlook 迷惑メール Email フィルターには、セーフリスト コレクションの設定が追加されています (たとえば、[差 **出人セーフ リストにメールを送信するユーザーを自動的に追加** する] など)。 詳細については、「[迷惑メール Email フィルターを使用して、表示されるメッセージを制御する」を参照してください](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077)。

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

Outlook で使用できる、クライアント側の迷惑メール フィルター設定を有効にしたり、無効ににしたり、構成したりするには、グループ ポリシーを使用します。 詳細については、「[管理用テンプレート ファイル (ADMX/ADML) と Office カスタマイズ ツール for Microsoft 365 Apps for enterprise、Office 2019、Office 2016」および](https://www.microsoft.com/download/details.aspx?id=49030)「[グループ ポリシーを使用して、差出人セーフ リストなどの迷惑メール設定を展開する方法](https://support.microsoft.com/help/2252421)」を参照してください。

Outlook 迷惑メール Email フィルターが既定値に設定されている場合、[**ホーム** \> **迷惑** \> **メールメール オプション] オプション**\>の **[自動フィルターなし**] に設定されている場合、Outlook はメッセージをスパムとして分類しませんが、セーフリスト コレクション ([差出人セーフ リスト]、[差出人セーフ リスト]、および [受信拒否リスト] リスト) を使用して、配信後に迷惑Email フォルダーにメッセージを移動します。 これらの設定の詳細については、「[迷惑メール Email フィルターの概要](https://support.microsoft.com/office/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089)」を参照してください。

> [!NOTE]
> Microsoft 365 組織では、EOP からのスパム フィルターの判定で不要な競合 (正と負の両方) を防ぐために、Outlook の迷惑メール Email フィルターを **自動フィルター処理なし** に設定しておくことをお勧めします。

Outlook の迷惑メール フィルターが **[低]** または **[高]** に設定されている場合、Outlook の迷惑メール フィルターでは、独自の SmartScreen フィルター テクノロジを使用して、迷惑メールを識別し、[迷惑メール] フォルダーに移動します。 このスパム分類は、EOP によって決定されるスパム信頼レベル (SCL) とは別です。 実際、Outlook は EOP からの SCL を無視し (EOP がメッセージにスパム フィルターをスキップするようにマークしていない限り)、独自の条件を使用してメッセージがスパムであるかどうかを判断します。 もちろん、EOP と Outlook からのスパムの判定が同じである可能性があります。 これらの設定の詳細については、「[迷惑メール Email フィルターで保護レベルを変更する](https://support.microsoft.com/office/e89c12d8-9d61-4320-8c57-d982c8d52f6b)」を参照してください。

> [!NOTE]
> 2016 年 11 月、Microsoft は、Exchange と Outlook の SmartScreen フィルターのスパム定義更新プログラムの生成を停止しました。 既存の SmartScreen スパム定義は残されていましたが、その有効性は時間の経過と共に低下する可能性があります。 詳細については、「[Outlook と Exchange での SmartScreen サポートの廃止](https://techcommunity.microsoft.com/t5/exchange-team-blog/deprecating-support-for-smartscreen-in-outlook-and-exchange/ba-p/605332)」 をご覧ください。

そのため、Outlook 迷惑メール Email フィルターは、メールボックスのセーフリスト コレクションと独自のスパム分類を使用して、迷惑メール Email フォルダーにメッセージを移動できます。

Outlook と Web 上の Outlook の両方で、セーフリスト コレクションがサポートされます。 セーフリスト コレクションはExchange Onlineメールボックスに保存されるため、Outlook のセーフリスト コレクションに対する変更はOutlook on the webに表示され、その逆も同様です。

## <a name="limits-for-junk-email-settings"></a>迷惑メール設定の制限

ユーザーのメールボックスに格納されているセーフリスト コレクション ([差出人セーフ リスト]、[差出人セーフ リスト]、および [ブロックされた送信者] の一覧) も EOP に同期されます。 ディレクトリ同期では、セーフリスト コレクションが Azure AD に同期されます。

- ユーザーのメールボックス内のセーフリスト コレクションには、すべてのリストと追加の迷惑メール フィルター設定を含む 510 KB の制限があります。 ユーザーがこの制限を超えると、次のような Outlook エラーが表示されます。

  > サーバーの迷惑メール リストに追加できない/できない。 サーバーで許可されているサイズを超えています。 迷惑メール リストがサーバーで許可されているサイズに縮小されるまで、サーバー上の迷惑メール フィルターは無効になります。

  この制限とその変更方法の詳細については、 [KB2669081](https://support.microsoft.com/help/2669081) を参照してください。

- EOP の同期セーフリスト コレクションには、次の同期制限があります。
  - [差出人セーフ リスト]、[差出人セーフ リスト]、および [連絡先 **からの信頼メール** ] が有効になっている場合の外部連絡先の合計エントリ数は 1024 個です。
  - [ブロックされた送信者] リストと [ブロックされたドメイン] リストの合計エントリ数は 500 個です。

  1024 エントリの制限に達すると、次のことが発生します。

  - リストは PowerShell とOutlook on the webのエントリの受け入れを停止しますが、エラーは表示されません。

    Outlook ユーザーは、Outlook の上限である 510 KB に達するまで、引き続き 1024 を超えるエントリを追加できます。 EOP フィルターがメールボックスへの配信前にメッセージをブロックしない限り、Outlook ではこれらの追加エントリを使用できます (メール フロー ルール、スプーフィング対策など)。

- ディレクトリ同期では、エントリは次の順序で Azure AD に同期されます。
  1. 連絡先からの信頼メールが有効になっている場合 **は、連絡先にメールを送信します** 。
  2. 差出人セーフ リストと差出人セーフ リストは、最初の 1024 エントリに対して変更が行われるたびに、組み合わされ、重複除去され、並べ替えられます。

  最初の 1024 エントリが使用され、関連情報がメッセージ ヘッダーにスタンプされます。

  Azure AD に同期されなかった 1024 を超えるエントリは Outlook によって処理され (Outlook on the webされません)、メッセージ ヘッダーに情報はスタンプされません。

ご覧のように、[ **連絡先からのメールを信頼** する] 設定を有効にすると、同期できる差出人セーフ センダーとセーフ 受信者の数が減ります。 これが懸念される場合は、グループ ポリシーを使用してこの機能をオフにすることをお勧めします。

- ファイル名: outlk16.opax
- ポリシー設定: **連絡先からの電子メールを信頼する**
