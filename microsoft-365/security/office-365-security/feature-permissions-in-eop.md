---
title: EOP の機能アクセス許可
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Microsoft Exchange Online Protection (EOP) を管理するタスクを実行するために必要なアクセス許可は、管理している機能に応じて異なります。
ms.openlocfilehash: 146bf34f157eb30e680ad9e0c3e53501d6e7b425
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2020
ms.locfileid: "43638120"
---
# <a name="feature-permissions-in-eop"></a>EOP の機能アクセス許可

Exchange Online Protection (EOP) を管理するタスクを実行するために必要なアクセス許可は、管理している機能によって異なります。

EOP をセットアップするには、グローバル管理者、または Exchange 会社の管理者 (Organization Management 役割グループ) である必要があります。

## <a name="exchange-online-protection-permissions"></a>Exchange Online Protection アクセス許可

EOP 機能を管理するために必要なアクセス許可は、次の表で確認してください。機能が複数の役割グループを示している場合、その機能を使用する役割グループを 1 つだけが割り当てる必要があります。

|**機能**|**必要なアクセス許可**|
|:-----|:-----|
|マルウェア対策|組織の管理 <br/><br/> 検疫管理|
|スパム対策|組織の管理 <br/><br/> 検疫管理|
|メール フロー ルール|組織の管理 <br/><br/> レコード管理|
|ドメイン|組織の管理 <br/><br/> 表示専用組織の管理|
|Advanced Threat Protection (ATP)|組織の管理 <br/><br/> 検疫管理|
|Microsoft 365 コネクタ|組織の管理|
|メッセージ追跡|組織の管理 <br/><br/> 表示専用組織の管理|
|組織の構成|組織の管理|
|Quarantine|組織の管理 <br/><br/> 表示専用組織の管理 <br/><br/> 検疫管理|
|ユーザー、連絡先、および役割グループ|組織の管理 <br/><br/> 表示専用組織の管理 <br/><br/> 検疫管理|
|配布グループとセキュリティ グループ|組織の管理 <br/><br/> 表示専用組織の管理 <br/><br/> 検疫管理|
|レポートの表示|組織の管理: メール保護レポートへのアクセス。 <br/><br/> 表示専用受信者: メール保護レポートへのアクセス。  <br/><br/> コンプライアンス管理: メール保護レポートおよびデータ損失防止 (DLP) レポートへのアクセス (サブスクリプションに DLP 機能が含まれている場合)。|
