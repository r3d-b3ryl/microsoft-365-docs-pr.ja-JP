---
title: Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
search.appverid: ''
ms.assetid: 421f72bd-dd43-4be1-82f5-0ae9ac43bd00
ms.custom:
- seo-marvel-apr2020
ROBOTS: noindex,nofollow
description: 削除済みメールボックス (回復可能) のインプレース ホールドを非アクティブにして、その内容を保存する方法について説明します。
ms.openlocfilehash: 0746081db76bd5b21947ff20ff7615f09cc08ba4
ms.sourcegitcommit: f3c912780bbcf5a5b47de192202adb3afbd5952b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/26/2022
ms.locfileid: "62218911"
---
# <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-in-exchange-online"></a>Exchange Online の削除済みメールボックス (回復可能) にインプレース ホールドを適用する

削除済みメールボックス (回復可能) のインプレース ホールドを非アクティブにして、その内容を保存する方法について説明します。Microsoft 電子情報開示ツールを使用して、非アクティブなメールボックスを検索できるようになります。

> [!IMPORTANT]
> メールボックス コンテンツを保持するためのさまざまな方法で投資を続ける中で、Exchange 管理センター (EAC) で In-Place Holds の削除を発表します。 2020 年 7 月 1 日以降、Exchange Online で新しいインプレース ホールドを作成することはできなくなります。 ただし、EAC または PowerShell の **Set-MailboxSearch** コマンドレットを使用して、EAC In-Place保持を管理Exchange Onlineできます。 ただし、2020 年 10 月 1 日から、保留の管理In-Placeされます。 削除できるのは、EAC または **Remove-MailboxSearch コマンドレットを使用する場合** のみです。 インプレース ホールドの廃止に関する詳細情報は、「[従来の eDiscovery ツールの廃止](legacy-ediscovery-retirement.md)」を参照してください。

You might have a situation where a person has left your organization, and their corresponding user account and mailbox were deleted. Afterwards, you realize there's information in the mailbox that needs to be preserved. What can you do? 削除されたメールボックスの保持期間の有効期限が切れていない場合は、削除されたメールボックス (回復可能な削除済みメールボックスと呼ばれる) に In-Place 保留を設定し、非アクティブなメールボックスにできます。 An  *inactive mailbox*  is used to preserve a former employee's email after he or she leaves your organization. The contents of an inactive mailbox are preserved for the duration of the In-Place Hold that was is placed on the soft-deleted mailbox when it was made inactive. メールボックスを非アクティブにした後、メールボックスの電子情報開示ツールを使用してメールボックスを検索Microsoft 365 コンプライアンス センター。

> [!NOTE]
> Exchange Online では、削除済みメールボックス (回復可能) は、メールボックスが削除されていても、特定の保存期間内であれば回復することができます。Exchange Online の削除済みメールボックス (回復可能) の保存期間は 30 日です。つまり、削除してから 30 日以内なら、メールボックスは復元できます (または、非アクティブなメールボックスにできます)。30 日が経過すると、削除済みメールボックスには完全削除のマークが付けられ、回復または非アクティブにすることができなくなります。

## <a name="requirements-for-in-place-holds"></a>ユーザー保持In-Place要件

- 削除済みメールボックス (回復可能) にインプレース ホールドを設定するには、Windows PowerShell で **New-MailboxSearch** コマンドレットを使う必要があります。Exchange 管理センター (EAC) または SharePoint Online の電子情報開示センターを使用することはできません。

- Windows PowerShell を使って Exchange Online に接続する方法については、「[Exchange Online PowerShell への接続](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- 組織内の削除済みメールボックス (回復可能) の識別情報を取得するには、次のコマンドを実行します。

  ```powershell
  Get-Mailbox -SoftDeletedMailbox | FL Name,WhenSoftDeleted,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

- 非アクティブなメールボックスの詳細については、「非アクティブな [メールボックスについて」を参照してください](inactive-mailboxes-in-office-365.md)。

## <a name="put-an-in-place-hold-on-a-soft-deleted-mailbox-to-make-it-an-inactive-mailbox"></a>削除済みメールボックス (回復可能) にインプレース ホールドを適用し、非アクティブなメールボックスにする

**New-MailboxSearch** コマンドレットを使用して、削除済みメールボックス (回復可能) を非アクティブなメールボックスにします。詳細については、「 [New-MailboxSearch](/powershell/module/exchange/new-mailboxsearch)」を参照してください。

1. 削除済みメールボックス (回復可能) のプロパティを含む変数を作成します。

   ```powershell
   $SoftDeletedMailbox = Get-Mailbox -SoftDeletedMailbox -Identity <identity of soft-deleted mailbox>
   ```

    > [!IMPORTANT]
    > 上記のコマンドでは、 **DistinguishedName** または **ExchangeGuid** プロパティの値を使用して削除済みメールボックス (回復可能) を識別します。これらのプロパティは組織内の各メールボックスに対して一意ですが、アクティブなメールボックスと削除済みメールボックス (回復可能) でプライマリ SMTP アドレスが等しい可能性があります。

2. インプレース ホールドを作成し、削除済みメールボックス (回復可能) に適用します。この例では、保存期間が指定されていません。この場合、アイテムは無制限に、または非アクティブなメールボックスからホールドが解除されるまで保存されます。

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true
    ```

   インプレース ホールドを作成するときに、保存期間を指定することもできます。この例では、非アクティブなメールボックスのアイテムを約 7 年間保持します。

   ```powershell
   New-MailboxSearch -Name "InactiveMailboxHold" -SourceMailboxes $SoftDeletedMailbox.DistinguishedName -InPlaceHoldEnabled $true -ItemHoldPeriod 2777
   ```

3. しばらくしてから、次のコマンドのいずれかを実行して削除済みメールボックス (回復可能) が、非アクティブなメールボックスになっていることを確認します。

   ```powershell
   Get-Mailbox -InactiveMailboxOnly
   ```

    または

   ```powershell
   Get-Mailbox -InactiveMailboxOnly -Identity $SoftDeletedMailbox.DistinguishedName  | FL IsInactiveMailbox
   ```

## <a name="more-information"></a>詳細情報

削除済みメールボックス (回復可能) を非アクティブなメールボックスにしてから、いろいろな方法でメールボックスを管理することができます。詳細については、以下を参照してください。

- [非アクティブなメールボックスの保持期間を変更する](change-the-hold-duration-for-an-inactive-mailbox.md)

- [非アクティブなメールボックスを回復する](recover-an-inactive-mailbox.md)

- [非アクティブなメールボックスを復元する](restore-an-inactive-mailbox.md)

- [非アクティブなメールボックスを削除](delete-an-inactive-mailbox.md) する (保留リストを削除して)