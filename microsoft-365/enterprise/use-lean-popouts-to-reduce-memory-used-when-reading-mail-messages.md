---
title: リーンポップアウトを使用してメールメッセージの読み取り時に使用されるメモリを削減する
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
description: この記事では、リーンポップアウトを使用して Outlook on the web でメッセージダウンロードのパフォーマンスを向上させる方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7bf53464ac6b2783fbbfc335fd4ff73dbe4435fb
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692110"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>リーンポップアウトを使用してメールメッセージの読み取り時に使用されるメモリを削減する

この記事では、Outlook on the web でのメッセージダウンロードのパフォーマンスを向上させる方法について説明します。 この記事は、 [Office 365 プロジェクトのネットワーク計画とパフォーマンスチューニング](https://aka.ms/tune) に含まれています。
  
Office 365 のグローバル管理者として、Outlook on the web を構成して、Microsoft Edge または Internet Explorer で特定の電子メール _メッセージをより_小さく、より小さなメモリを消費するバージョンにすることができます。 Web 上の Outlook に対してリーンポップアウトが構成されている場合、サーバー側でレンダリングされるコンポーネントはパフォーマンスを最適化するために読み込まれます。
  
> [!NOTE]
> 2018年3月の間、Information rights Management (IRM) などの使用権限の制限を指定するメッセージでは、リーンポップアウトは使用できません。
  
これらの機能は、メインウィンドウでは引き続き動作しますが、リーン popouts では使用できません。
  
- Outlook アドイン
  
- Skype for Business のプレゼンス
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Office 365 組織内のすべてのユーザーのリーンポップアウトを構成するには
  
1. [リモート PowerShell を使用して Exchange Online に接続](https://technet.microsoft.com/library/jj984289%28v=exchg.150%29.aspx )します。
  
2. LeanPopoutEnabled パラメーターを使用して、次のように [コマンドレットを実行します](https://technet.microsoft.com/library/aa997443%28v=exchg.160%29.aspx) 。

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  たとえば、組織内のすべてのユーザーのリーンポップアウトを有効にするには、次のように入力します。
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  組織内のすべてのユーザーのリーンポップアウトを無効にするには、次のようにします。

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
