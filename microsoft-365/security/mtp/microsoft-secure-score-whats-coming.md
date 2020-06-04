---
title: Microsoft セキュア スコアの新機能
description: Microsoft 365 セキュリティ センターの Microsoft セキュア スコアについて、詳細をどのように計算するか、セキュリティ管理者がどんなことを期待できるかについて説明します。
keywords: セキュリティ、マルウェア、Microsoft 365、M365、セキュア スコア、セキュリティ センター、改善アクション
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f9bca47c6a47468d0a5a37b77e4f587745bf619d
ms.sourcegitcommit: c696852da06d057dba4f5147bbf46521910de3ab
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/03/2020
ms.locfileid: "44545936"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="ec008-104">Microsoft セキュア スコアの新機能</span><span class="sxs-lookup"><span data-stu-id="ec008-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="ec008-105">Microsoft のセキュリティ[スコア](microsoft-secure-score-new.md)をより良いものにして、セキュリティの状況をより良くし、利便性を向上させるために、近い将来にいくつかの変更を加えています。</span><span class="sxs-lookup"><span data-stu-id="ec008-105">To make [Microsoft Secure Score](microsoft-secure-score-new.md) a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="ec008-106">お客様のスコアと最大可能スコアが新しくなります。</span><span class="sxs-lookup"><span data-stu-id="ec008-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="ec008-107">ただし、これによりセキュリティ体制が変わるわけではありません。</span><span class="sxs-lookup"><span data-stu-id="ec008-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="ec008-108">最近の変更については、「[Microsoft セキュア スコアの新機能](microsoft-secure-score-new.md#whats-new)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ec008-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score-new.md#whats-new)</span></span>

## <a name="june-2020"></a><span data-ttu-id="ec008-109">2020年6月</span><span class="sxs-lookup"><span data-stu-id="ec008-109">June 2020</span></span>

### <a name="remove-improvement-action-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="ec008-110">Microsoft Defender Advanced Threat Protection の改善アクションを削除する</span><span class="sxs-lookup"><span data-stu-id="ec008-110">Remove improvement action for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="ec008-111">Attack Surface Reduction ルールを有効にする</span><span class="sxs-lookup"><span data-stu-id="ec008-111">Turn on Attack Surface Reduction rules</span></span>

### <a name="add-improvement-actions-for-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="ec008-112">Microsoft Defender Advanced Threat Protection の改善アクションを追加する</span><span class="sxs-lookup"><span data-stu-id="ec008-112">Add improvement actions for Microsoft Defender Advanced Threat Protection</span></span>

* <span data-ttu-id="ec008-113">Adobe Reader が子プロセスを作成するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="ec008-113">Block Adobe Reader from creating child processes</span></span>
* <span data-ttu-id="ec008-114">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="ec008-114">Use advanced protection against ransomware</span></span>
* <span data-ttu-id="ec008-115">すべての Office アプリケーションで子プロセスを作成することを禁止する</span><span class="sxs-lookup"><span data-stu-id="ec008-115">Block all Office applications from creating child processes</span></span>
* <span data-ttu-id="ec008-116">Office アプリケーションで実行可能なコンテンツを作成することを禁止する</span><span class="sxs-lookup"><span data-stu-id="ec008-116">Block Office applications from creating executable content</span></span>
* <span data-ttu-id="ec008-117">JavaScript または VBScript がダウンロードされた実行可能コンテンツを起動するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="ec008-117">Block JavaScript or VBScript from launching downloaded executable content</span></span>
* <span data-ttu-id="ec008-118">難読化する可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="ec008-118">Block execution of potentially obfuscated scripts</span></span>
* <span data-ttu-id="ec008-119">電子メールクライアントおよび webmail からの実行可能ファイルのコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="ec008-119">Block executable content from email client and webmail</span></span>
* <span data-ttu-id="ec008-120">Office コミュニケーションアプリケーションによる子プロセスの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="ec008-120">Block Office communication application from creating child processes</span></span>
* <span data-ttu-id="ec008-121">USB から実行される信頼できないおよび署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="ec008-121">Block untrusted and unsigned processes that run from USB</span></span>
* <span data-ttu-id="ec008-122">WMI イベントサブスクリプション経由の永続化をブロックする</span><span class="sxs-lookup"><span data-stu-id="ec008-122">Block persistence through WMI event subscription</span></span>
* <span data-ttu-id="ec008-123">Office アプリケーションが他のプロセスにコードを挿入するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="ec008-123">Block Office applications from injecting code into other processes</span></span>
* <span data-ttu-id="ec008-124">実行可能ファイルが、流行、年齢、または信頼できるリストの条件を満たしていない限り、実行を禁止する</span><span class="sxs-lookup"><span data-stu-id="ec008-124">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
* <span data-ttu-id="ec008-125">PSExec および WMI コマンドからのプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="ec008-125">Block process creations originating from PSExec and WMI commands</span></span>
* <span data-ttu-id="ec008-126">Windows ローカルセキュリティ機関サブシステム (lsass.exe) からの資格情報の盗用をブロックする</span><span class="sxs-lookup"><span data-stu-id="ec008-126">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
* <span data-ttu-id="ec008-127">Office マクロからの Win32 API 呼び出しをブロックする</span><span class="sxs-lookup"><span data-stu-id="ec008-127">Block Win32 API calls from Office macros</span></span>
