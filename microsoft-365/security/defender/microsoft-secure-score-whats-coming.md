---
title: Microsoft Secure Score に関する情報
description: セキュリティ センターで Microsoft Secure Score に加わる新しい変更Microsoft 365説明します。
keywords: microsoft secure score, secure score, office 365 secure score, microsoft security score, microsoft 365 security center, improvement actions
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 910eb16ad33555ca61875a346b50cea7e63b2220
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/08/2021
ms.locfileid: "53338555"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="423c9-104">Microsoft Secure Score に関する情報</span><span class="sxs-lookup"><span data-stu-id="423c9-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="423c9-105">Microsoft Secure Score は、セキュリティ https://security.microsoft.com/securescore センターのMicrosoft 365[にあります](overview-security-center.md)。</span><span class="sxs-lookup"><span data-stu-id="423c9-105">Microsoft Secure Score can be found at https://security.microsoft.com/securescore in the [Microsoft 365 security center](overview-security-center.md).</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="423c9-106">Proposed changes</span><span class="sxs-lookup"><span data-stu-id="423c9-106">Proposed changes</span></span>

<span data-ttu-id="423c9-107">Microsoft [Secure Score](microsoft-secure-score.md) をセキュリティの姿勢をより良くし、使いやすさを向上させるために、近い将来、いくつかの変更を加えています。</span><span class="sxs-lookup"><span data-stu-id="423c9-107">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="423c9-108">スコアと可能な最大スコアが変更される場合があります。</span><span class="sxs-lookup"><span data-stu-id="423c9-108">Your score and the maximum possible score may change.</span></span>

### <a name="july-2021"></a><span data-ttu-id="423c9-109">2021 年 7 月</span><span class="sxs-lookup"><span data-stu-id="423c9-109">July 2021</span></span>

#### <a name="add-improvement-action-related-to-microsoft-teams"></a><span data-ttu-id="423c9-110">ユーザーに関連する改善アクションをMicrosoft Teams</span><span class="sxs-lookup"><span data-stu-id="423c9-110">Add improvement action related to Microsoft Teams</span></span>

- <span data-ttu-id="423c9-111">ダイヤルイン ユーザーが会議ロビーをバイパスするのを制限します。</span><span class="sxs-lookup"><span data-stu-id="423c9-111">Restrict dial-in users from bypassing a meeting lobby.</span></span>
- <span data-ttu-id="423c9-112">外部参加者が会議で制御を持つことをTeamsします。</span><span class="sxs-lookup"><span data-stu-id="423c9-112">Limit external participants from having control in a Teams meeting.</span></span>
- <span data-ttu-id="423c9-113">匿名ユーザーによる会議の開始Teams制限します。</span><span class="sxs-lookup"><span data-stu-id="423c9-113">Restrict anonymous users from starting Teams meetings.</span></span>
- <span data-ttu-id="423c9-114">会議に対してロビーをセットアップTeamsします。</span><span class="sxs-lookup"><span data-stu-id="423c9-114">Require lobbies to be set up for Teams meetings.</span></span>
- <span data-ttu-id="423c9-115">会議に参加できるユーザーをTeamsします。</span><span class="sxs-lookup"><span data-stu-id="423c9-115">Configure which users are allowed to be present in Teams meetings.</span></span>

#### <a name="add-improvement-action-related-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="423c9-116">エンドポイント用 Microsoft Defender に関連する改善アクションを追加する</span><span class="sxs-lookup"><span data-stu-id="423c9-116">Add improvement action related to Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="423c9-117">MacOS 用の Microsoft Defender for Endpoint センサー データ収集を修正する</span><span class="sxs-lookup"><span data-stu-id="423c9-117">Fix Microsoft Defender for Endpoint sensor data collection for macOS</span></span>
- <span data-ttu-id="423c9-118">MacOS の Microsoft Defender for Endpoint 障害のある通信を修正する</span><span class="sxs-lookup"><span data-stu-id="423c9-118">Fix Microsoft Defender for Endpoint impaired communications for macOS</span></span>
- <span data-ttu-id="423c9-119">macOS でパスワードの最小長を 15 文字以上に設定する</span><span class="sxs-lookup"><span data-stu-id="423c9-119">Set minimum password length to 15 or more characters in macOS</span></span>
- <span data-ttu-id="423c9-120">macOS で 'パスワード履歴を強制する' を '24 以上のパスワード' に設定する</span><span class="sxs-lookup"><span data-stu-id="423c9-120">Set 'Enforce password history' to '24 or more password(s)' in macOS</span></span>
- <span data-ttu-id="423c9-121">macOS で '最大パスワード期間' を '90 以下の日数に設定するが、0 には設定しない]</span><span class="sxs-lookup"><span data-stu-id="423c9-121">Set 'Maximum password age' to '90 or fewer days, but not 0' in macOS</span></span>
- <span data-ttu-id="423c9-122">macOS でアカウントロックアウトのしきい値を 5 以下に設定する</span><span class="sxs-lookup"><span data-stu-id="423c9-122">Set account lockout threshold to 5 or lower in macOS</span></span>
- <span data-ttu-id="423c9-123">macOS でファイアウォールを有効にする</span><span class="sxs-lookup"><span data-stu-id="423c9-123">Turn on Firewall on macOS</span></span>
- <span data-ttu-id="423c9-124">ゲートキーパーを有効にする</span><span class="sxs-lookup"><span data-stu-id="423c9-124">Enable Gatekeeper</span></span>
- <span data-ttu-id="423c9-125">システム整合性保護 (SIP) を有効にする</span><span class="sxs-lookup"><span data-stu-id="423c9-125">Enable System Integrity Protection (SIP)</span></span>
- <span data-ttu-id="423c9-126">FileVault ディスク暗号化を有効にする</span><span class="sxs-lookup"><span data-stu-id="423c9-126">Enable FileVault Disk Encryption</span></span>
- <span data-ttu-id="423c9-127">macOS でスクリーンセーバーが起動するときに画面をロックする</span><span class="sxs-lookup"><span data-stu-id="423c9-127">Set screen to lock when screensaver starts in macOS</span></span>
- <span data-ttu-id="423c9-128">macOS でスクリーンセーバーが 20 分以下で開始する設定を確認する</span><span class="sxs-lookup"><span data-stu-id="423c9-128">Ensure screensaver is set to start in 20 minutes or less in macOS</span></span>
- <span data-ttu-id="423c9-129">ホーム フォルダーのセキュリティ保護</span><span class="sxs-lookup"><span data-stu-id="423c9-129">Secure Home Folders</span></span>
- <span data-ttu-id="423c9-130">macOS のMicrosoft Defender ウイルス対策保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="423c9-130">Turn on Microsoft Defender Antivirus real-time protection for macOS</span></span>
- <span data-ttu-id="423c9-131">macOS のMicrosoft Defender ウイルス対策 PUA 保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="423c9-131">Turn on Microsoft Defender Antivirus PUA protection in block mode for macOS</span></span>
- <span data-ttu-id="423c9-132">macOS Microsoft Defender ウイルス対策クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="423c9-132">Enable Microsoft Defender Antivirus cloud-delivered protection for macOS</span></span>
- <span data-ttu-id="423c9-133">macOS Microsoft Defender ウイルス対策定義を更新する</span><span class="sxs-lookup"><span data-stu-id="423c9-133">Update Microsoft Defender Antivirus definitions for macOS</span></span>
- <span data-ttu-id="423c9-134">Microsoft Defender for Endpoint sensor data collection for Linux の修正</span><span class="sxs-lookup"><span data-stu-id="423c9-134">Fix Microsoft Defender for Endpoint sensor data collection for Linux</span></span>
- <span data-ttu-id="423c9-135">Linux 用の Microsoft Defender for Endpoint 障害のある通信を修正する</span><span class="sxs-lookup"><span data-stu-id="423c9-135">Fix Microsoft Defender for Endpoint impaired communications for Linux</span></span>
- <span data-ttu-id="423c9-136">制限されていないアクセス アカウント</span><span class="sxs-lookup"><span data-stu-id="423c9-136">Unrestricted Access Accounts</span></span>
- <span data-ttu-id="423c9-137">Linux のMicrosoft Defender ウイルス対策保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="423c9-137">Turn on Microsoft Defender Antivirus real-time protection for Linux</span></span>
- <span data-ttu-id="423c9-138">Linux のブロック Microsoft Defender ウイルス対策 PUA 保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="423c9-138">Turn on Microsoft Defender Antivirus PUA protection in block mode for Linux</span></span>
- <span data-ttu-id="423c9-139">Linux Microsoft Defender ウイルス対策クラウドによる保護を有効にする</span><span class="sxs-lookup"><span data-stu-id="423c9-139">Enable Microsoft Defender Antivirus cloud-delivered protection for Linux</span></span>
- <span data-ttu-id="423c9-140">Linux Microsoft Defender ウイルス対策定義を更新する</span><span class="sxs-lookup"><span data-stu-id="423c9-140">Update Microsoft Defender Antivirus definitions for Linux</span></span>



## <a name="related-resources"></a><span data-ttu-id="423c9-141">関連リソース</span><span class="sxs-lookup"><span data-stu-id="423c9-141">Related resources</span></span>

- [<span data-ttu-id="423c9-142">Microsoft Secure Score の概要</span><span class="sxs-lookup"><span data-stu-id="423c9-142">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="423c9-143">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="423c9-143">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="423c9-144">Microsoft Secure Score の履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="423c9-144">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="423c9-145">新機能</span><span class="sxs-lookup"><span data-stu-id="423c9-145">What's new</span></span>](microsoft-secure-score-whats-new.md)
