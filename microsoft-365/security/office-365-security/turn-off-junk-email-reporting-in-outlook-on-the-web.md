---
title: Outlook on the web で迷惑メール レポートを無効にする
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 8d57fe9e-57b8-4884-9317-80b380804b4a
ms.collection:
- M365-security-compliance
description: Office 365 管理者は、ユーザーが迷惑メールとして電子メールを報告する機能をオフにできます。
ms.openlocfilehash: 46ce4de8fa6ea14c81041208864957cbc73aebf5
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871283"
---
# <a name="turn-off-junk-email-reporting-in-outlook-on-the-web"></a>Outlook on the web で迷惑メール レポートを無効にする

Web 上の outlook on the web (以前の outlook Web App) の迷惑メール報告オプションを使用して、outlook on the web[上](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)の outlook on the web を使用して分析することができます。 これらのオプションを使用しない場合は、管理者[は、次のコマンドレット](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)を使用してオフにすることができます。

## <a name="what-do-you-need-to-know-before-you-begin"></a>始める前に把握しておくべき情報
<a name="sectionSection0"> </a>

- 予想所要時間 : 5 分

- この手順を実行する際には、あらかじめアクセス許可を割り当てる必要があります。 必要なアクセス許可については、「 [Exchange Online のアクセス許可](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions#exchange-online-permissions)」の「web 上の Outlook メールボックスポリシー」を参照してください。

- Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。

## <a name="turn-off-junk-phishing-and-not-junk-reporting-to-microsoft"></a>迷惑メール報告をオフにして Microsoft に通知しない
<a name="sectionSection1"> </a>

最初に、次のコマンドを実行して、web メールボックスポリシーで利用可能な Outlook の名前を取得します。

```
Get-OwaMailboxPolicy | Format-Table Name
```

次に、以下の構文を使用して、Outlook on the web で迷惑メール報告を Microsoft に対して有効または無効にします。

```
Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
```

この例では、既定の Outlook web app メールボックスポリシーでのレポートをオフにします。

```
Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
```

構文およびパラメーターの詳細については、「[収集](https://docs.microsoft.com/powershell/module/exchange/client-access/get-owamailboxpolicy)」を[参照してください。](https://docs.microsoft.com/powershell/module/exchange/client-access/set-owamailboxpolicy)

## <a name="how-do-you-know-this-worked"></a>正常な動作を確認する方法
<a name="sectionSection2"> </a>

**Get-Owamare Boxpolicy**を実行してパラメーター値を確認した後、影響を受けるユーザー (web 上の outlook メールボックスポリシーが適用されているユーザー) に対して web 上の outlook を開き、迷惑メールを報告するオプションが使用できないことを確認します。 引き続き迷惑メール、フィッシング、および迷惑メールとしてメッセージをマークすることはできますが、それらを報告することはできません。
