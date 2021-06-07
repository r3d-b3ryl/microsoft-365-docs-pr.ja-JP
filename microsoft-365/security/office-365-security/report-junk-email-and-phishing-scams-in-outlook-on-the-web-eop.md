---
title: Web で迷惑メールやフィッシングメールをOutlookメールを報告する
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: 管理者は、Exchange Online の web (Outlook Web App) の Outlook の組み込みの迷惑メール、迷惑メール、フィッシングメール報告オプション、およびユーザーに対してこれらのレポート オプションを無効にする方法について説明します。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788309"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a>迷惑メールとフィッシングメールを web Outlookで報告するExchange Online

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**適用対象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 プラン 1 およびプラン 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

ハイブリッドモダン認証を使用して Exchange Online またはオンプレミスのメールボックスにメールボックスを持つ Microsoft 365[](../../enterprise/hybrid-modern-auth-overview.md)組織では、誤検知 (スパムとしてマークされた良い電子メール)、偽陰性 (悪い電子メールが許可されている)、フィッシング メッセージを Exchange Online Protection (EOP) に送信できます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

> [!IMPORTANT]
> ユーザー申請には、レポート メッセージ アドインまたはレポート フィッシング アドインをお勧めします。 詳細については、「レポート メッセージまたはレポート フィッシング アドインを有効にする[」を参照してください](./enable-the-report-message-add-in.md)。ユーザー申請ポリシーを使用できないので、Outlookの組み込みレポート エクスペリエンス[はお勧めしません](./user-submission.md)。

- ユーザーがメールボックスを使用している組織の管理者Exchange Online、コンプライアンス センターのセキュリティ &ポータルを使用することをお勧めします。 詳細については、「管理申請を [使用して疑わしいスパム、フィッシング、URL、](admin-submission.md)ファイルを Microsoft に提出する」を参照してください。

- 管理者は、ユーザーが Web 上で Microsoft にメッセージを報告する機能を無効Outlook有効にできます。 詳細については、この記事の後半の「Web サイトの迷惑Outlook[報告](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)を無効または有効にする」を参照してください。

- 指定したメールボックスにコピーまたはリダイレクトするレポート メッセージを構成できます。 詳細については、「ユーザー申請 [ポリシー」を参照してください](user-submission.md)。

- Microsoft へのメッセージの報告の詳細については、「メッセージとファイルを Microsoft に報告 [する」を参照してください](report-junk-email-messages-to-microsoft.md)。

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>Web 上の迷惑メール レポートを無効Outlook有効にする

既定では、ユーザーはスパムの誤検知、誤検知、およびフィッシング メッセージを Microsoft に報告して、web 上Outlook分析できます。 管理者は、Outlook PowerShell の Exchange Online Web メールボックス ポリシーでユーザーがスパムの誤検知やスパムの誤検知を Microsoft に報告し、そのポリシーを構成できます。 ユーザーがフィッシング メッセージを Microsoft に報告する機能を無効にできない。

### <a name="what-do-you-need-to-know-before-you-begin"></a>はじめに把握しておくべき情報

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。

- この記事の手順を実行するには、Exchange Onlineにアクセス許可を割り当てる必要があります。 具体的には、既定で **組織の管理** 役割グループと受信者管理役割グループに割り当てられている受信者ポリシーまたはメール受信者の役割が必要です。  グループ内の役割グループの詳細については、「Exchange Onlineのアクセス許可[](/exchange/permissions-exo/permissions-exo)」および「Exchange Online の役割グループの変更」[を参照Exchange Online。](/Exchange/permissions-exo/role-groups#modify-role-groups)

- すべての組織に OwaMailboxPolicy-Default という名前の既定のポリシーがありますが、カスタム ポリシーを作成できます。 カスタム ポリシーは、既定のポリシーの前にスコープ付きユーザーに適用されます。 Web メールボックス ポリシーのOutlook詳細については、「Outlookの Web メールボックス ポリシーの詳細」[を参照Exchange Online。](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)

- 迷惑メールレポートを無効にしても、メッセージを迷惑メールとしてマークしたり、Web 上の迷惑メールOutlook削除したりする機能は削除されません。 迷惑メール フォルダーでメッセージを選択し、[迷惑メールではない] をクリックすると、メッセージは受信トレイ \> に戻ります。 他のメール フォルダーでメッセージを選択し、[迷惑メール] をクリックすると、メッセージは [迷惑メール \> ] フォルダーに移動されます。 使用できなくなったのは、Microsoft にメッセージを報告するオプションです。

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a>PowerShell Exchange Onlineを使用して、Web 上の迷惑メール レポートを無効Outlook有効にする

1. Web メールボックス ポリシーと迷惑Outlookレポートの状態で既存のメール を検索するには、次のコマンドを実行します。

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. Web 上の迷惑メール レポートを無効Outlook有効にするには、次の構文を使用します。

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   この例では、既定のポリシーで迷惑メールレポートを無効にします。

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   この例では、Contoso Managers という名前のカスタム ポリシーで迷惑メール レポートを有効にします。

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

構文とパラメーターの詳細については [、「Get-OwaMailboxPolicy」](/powershell/module/exchange/get-owamailboxpolicy) および [「Set-OwaMailboxPolicy」を参照してください](/powershell/module/exchange/set-owamailboxpolicy)。

### <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法

Web 上で迷惑メールレポートが正常に有効または無効Outlookするには、次の手順を実行します。

- PowerShell Exchange Onlineで、次のコマンドを実行し **、ReportJunkEmailEnabled プロパティ** の値を確認します。

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- web 上の Outlook で影響を受けるユーザーのメールボックスを開き、受信トレイでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示されないか確認します。 \> <sup>\*</sup>

- web 上の Outlook で影響を受けるユーザーのメールボックスを開き、[迷惑メール] フォルダーでメッセージを選択し、[迷惑メール] をクリックして、メッセージを Microsoft に報告するか表示されないか確認します。 \> <sup>\*</sup>

<sup>\*</sup> ユーザーは、メッセージを報告しながらメッセージを報告するプロンプトを非表示にできます。 Web 上でこの設定Outlook確認するには、次の方法を実行します。

1. [web **設定Outlook]** アイコンをクリックして、[すべての設定 ![ を表示 ](../../media/owa-settings-icon.png) \> **Outlook迷惑メール** \> **] をクリックします**。
2. [レポート **] セクションで** 、値を確認します。 **レポートを送信する前に確認してください**。

   ![Outlook迷惑メールレポートの設定を確認する](../../media/owa-junk-email-reporting-options.png)
