---
title: ユーザーが Microsoft Defender AV を操作する方法を構成する
description: エンド ユーザーが Microsoft Defender AV とやり取りする方法、表示される通知、および設定を上書きできる場合を構成します。
keywords: endpoint, user, Interaction, notifications, ui lockdown mode, headless mode, hide interface
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: df9f87e725575bad2f36cf7b016d257e766e523b
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765229"
---
# <a name="configure-end-user-interaction-with-microsoft-defender-antivirus"></a><span data-ttu-id="814cf-104">Microsoft Defender ウイルス対策とのエンド ユーザー操作を構成する</span><span class="sxs-lookup"><span data-stu-id="814cf-104">Configure end-user interaction with Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="814cf-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="814cf-105">**Applies to:**</span></span>

- [<span data-ttu-id="814cf-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="814cf-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="814cf-107">ネットワーク上のエンドポイントのユーザーが Microsoft Defender ウイルス対策とやり取りする方法を構成できます。</span><span class="sxs-lookup"><span data-stu-id="814cf-107">You can configure how users of the endpoints on your network can interact with Microsoft Defender Antivirus.</span></span>

<span data-ttu-id="814cf-108">これには、Microsoft Defender ウイルス対策インターフェイスが表示されるかどうか、表示される通知、およびグローバルに展開されたグループ ポリシー設定をローカルで上書きできるかどうかが含まれます。</span><span class="sxs-lookup"><span data-stu-id="814cf-108">This includes whether they see the Microsoft Defender Antivirus interface, what notifications they see, and if they can locally override globally-deployed Group Policy settings.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="814cf-109">このセクションの内容</span><span class="sxs-lookup"><span data-stu-id="814cf-109">In this section</span></span>

<span data-ttu-id="814cf-110">トピック</span><span class="sxs-lookup"><span data-stu-id="814cf-110">Topic</span></span> | <span data-ttu-id="814cf-111">説明</span><span class="sxs-lookup"><span data-stu-id="814cf-111">Description</span></span> 
---|---
[<span data-ttu-id="814cf-112">エンドポイントに表示される通知を構成する</span><span class="sxs-lookup"><span data-stu-id="814cf-112">Configure notifications that appear on endpoints</span></span>](configure-notifications-microsoft-defender-antivirus.md) | <span data-ttu-id="814cf-113">追加の通知、通知用にカスタマイズされたテキスト、修復のための再起動に関する通知を構成およびカスタマイズする</span><span class="sxs-lookup"><span data-stu-id="814cf-113">Configure and customize additional notifications, customized text for notifications, and notifications about reboots for remediation</span></span>
[<span data-ttu-id="814cf-114">ユーザーが Microsoft Defender ウイルス対策ユーザー インターフェイスを表示または操作するのを防ぐ</span><span class="sxs-lookup"><span data-stu-id="814cf-114">Prevent users from seeing or interacting with the Microsoft Defender Antivirus user interface</span></span>](prevent-end-user-interaction-microsoft-defender-antivirus.md) | <span data-ttu-id="814cf-115">ユーザー インターフェイスをユーザーから非表示にする</span><span class="sxs-lookup"><span data-stu-id="814cf-115">Hide the user interface from users</span></span>
[<span data-ttu-id="814cf-116">ユーザーによるポリシー設定のローカル変更を防止する</span><span class="sxs-lookup"><span data-stu-id="814cf-116">Prevent users from locally modifying policy settings</span></span>](configure-local-policy-overrides-microsoft-defender-antivirus.md) | <span data-ttu-id="814cf-117">ユーザーが個々のエンドポイントでポリシー設定を上書きする (または許可する)</span><span class="sxs-lookup"><span data-stu-id="814cf-117">Prevent (or allow) users from overriding policy settings on their individual endpoints</span></span>