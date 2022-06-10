---
title: リーン ポップアウトを使用して、メール メッセージの読み取り時に使用されるメモリを減らす
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: この記事には、リーン ポップアウトを使用して、Outlook on the webでのメッセージダウンロードのパフォーマンスを向上させるための情報が含まれています。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9636fd3beafd169358c4b50cafdc4ac0f9494994
ms.sourcegitcommit: 133bf9097785309da45df6f374a712a48b33f8e9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/10/2022
ms.locfileid: "66012684"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a>リーン ポップアウトを使用して、メール メッセージの読み取り時に使用されるメモリを減らす

この記事には、Outlook on the webでのメッセージダウンロードのパフォーマンスを向上するための情報が含まれています。 この記事は、Office 365 プロジェクトの[ネットワーク計画とパフォーマンスのチューニングの](./network-planning-and-performance.md)一部です。
  
**Office 365アプリケーション管理者**、**グローバル管理者**、または **ユーザー管理者** は、Microsoft Edgeまたは Internet Explorer で _、無駄のないポップアップ_ を配信するようにOutlook on the webを構成できます。 Outlook on the web用にリーン ポップアウトを構成すると、サーバー側のレンダリングされたコンポーネントが読み込まれ、パフォーマンスが最適化されます。
  
> [!NOTE]
> 2018 年 3 月の時点では、情報Rights Management (IRM) などの使用権限の制限を指定するメッセージでは、リーン ポップアウトを使用できません。
  
これらの機能は引き続きメイン ウィンドウで機能しますが、リーン ポップアウトでは使用できません。
  
- Outlook アドイン
  
- Skype for Businessプレゼンス
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a>Office 365組織内のすべてのユーザーに対してリーン ポップアップを構成するには
  
1. [Exchange Online PowerShell に接続します](/powershell/exchange/connect-to-exchange-online-powershell)。
  
2. 次のように、LeanPopoutEnabled パラメーターを使用して [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) コマンドレットを実行します。

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  たとえば、組織内のすべてのユーザーに対してリーン ポップアップを有効にするには、次のようにします。
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  組織内のすべてのユーザーに対してリーン ポップアウトを無効にするには、

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```
