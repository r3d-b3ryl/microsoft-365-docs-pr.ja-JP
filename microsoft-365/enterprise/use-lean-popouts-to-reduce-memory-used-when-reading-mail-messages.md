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
description: この記事では、リーン ポップアウトを使用して Outlook on the web でのメッセージダウンロードのパフォーマンスを向上させる方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925258"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>無駄のないポップアウトを使用して、メール メッセージの読み取り時に使用されるメモリを削減する

この記事では、Outlook on the web でのメッセージダウンロードのパフォーマンスを向上させる方法について説明します。 この記事は [、365](./network-planning-and-performance.md) プロジェクトのネットワーク計画とパフォーマンスOfficeです。
  
Office 365 のグローバル管理者として、Microsoft Edge または Internet Explorer で特定の電子メール メッセージの無駄のないポップアウト 、より小さく、メモリ消費の少ないバージョンを配信する Outlook on the web を構成できます。 リーン ポップアウトが Outlook on the Web 用に構成されている場合、パフォーマンスを最適化するサーバー側レンダリング コンポーネントが読み込まれます。
  
> [!NOTE]
> 2018 年 3 月の現在、情報権利管理 (IRM) などの使用権限の制限を指定するメッセージでは、リーン ポップアウトを使用できません。
  
これらの機能はメイン ウィンドウで引き続き機能しますが、リーン ポップアウトでは使用できません。
  
- Outlook アドイン
  
- Skype for Business プレゼンス
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>365 組織内のすべてのユーザーにリーン ポップアウトをOfficeするには
  
1. [リモート PowerShell を使用して Exchange Online に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。
  
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