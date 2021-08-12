---
title: 無駄のないポップアウトを使用して、メール メッセージの読み取り時に使用されるメモリを削減する
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: この記事では、リーン ポップアウトを使用してメッセージダウンロードのパフォーマンスを向上させる方法についてOutlook on the web。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 612774478f5b649901d6eae9dccf332299fa53d38331c6ced847ea8d05be104e
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "53840769"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>無駄のないポップアウトを使用して、メール メッセージの読み取り時に使用されるメモリを削減する

この記事では、メッセージダウンロードのパフォーマンスを向上させる方法についてOutlook on the web。 この記事は、プロジェクトのネットワーク[計画とパフォーマンスの調整Office 365](./network-planning-and-performance.md)です。
  
Office 365 のグローバル管理者は、Outlook on the web または Microsoft Edge または Internet Explorerで特定の電子メール メッセージの小規模でメモリ負荷の少ないバージョンの無駄のないポップアウトを配信する Outlook on the web を構成できます。 リーン ポップアウトが Outlook on the web場合、パフォーマンスを最適化するサーバー側レンダリング コンポーネントが読み込まれます。
  
> [!NOTE]
> 2018 年 3 月の現在、情報権利管理 (IRM) などの使用権限の制限を指定するメッセージでは、リーン ポップアウトを使用できません。
  
これらの機能はメイン ウィンドウで引き続き機能しますが、リーン ポップアウトでは使用できません。
  
- Outlook アドイン
  
- Skype for Businessプレゼンス
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>組織内のすべてのユーザーにリーン ポップアウトをOffice 365するには
  
1. [Connect PowerShell をExchange Onlineする方法について説明します](/powershell/exchange/connect-to-exchange-online-powershell)。
  
2. 次のように、LeanPopoutEnabled パラメーターを使用して [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) コマンドレットを実行します。

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  たとえば、組織内のすべてのユーザーに対してリーン ポップアウトを有効にするには、次の方法を実行します。
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  組織内のすべてのユーザーに対してリーン ポップアウトを無効にするには、次の方法を使用します。

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```