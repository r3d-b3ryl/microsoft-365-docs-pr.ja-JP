---
title: Microsoft のセキュリティで保護されたスコア
description: Microsoft 365 セキュリティセンターで Microsoft セキュリティスコアに追加された新しい変更内容について説明します。
keywords: microsoft secure score、secure score、office 365 のセキュリティスコア、microsoft セキュリティスコア、microsoft 365 セキュリティセンター、改善アクション
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
ms.openlocfilehash: 82ec67cae86525c055b2232667cccb603830d15f
ms.sourcegitcommit: c51de5e1a4cb9c4a7a9854a4226b32453d9e73e0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48779250"
---
# <a name="whats-coming-to-microsoft-secure-score"></a><span data-ttu-id="5dfce-104">Microsoft のセキュリティで保護されたスコア</span><span class="sxs-lookup"><span data-stu-id="5dfce-104">What's coming to Microsoft Secure Score</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="5dfce-105">弊社では、セキュリティ上の姿勢をより良いものにするために、近日中に変更を行っており、利便性を向上 [さ](microsoft-secure-score.md) せています。</span><span class="sxs-lookup"><span data-stu-id="5dfce-105">We're making some changes in the near future to make [Microsoft Secure Score](microsoft-secure-score.md) a better representative of your security posture and improve usability.</span></span> <span data-ttu-id="5dfce-106">スコアと可能な最大スコアは変わる可能性があります。</span><span class="sxs-lookup"><span data-stu-id="5dfce-106">Your score and the maximum possible score may change.</span></span>

## <a name="proposed-changes"></a><span data-ttu-id="5dfce-107">Proposed changes</span><span class="sxs-lookup"><span data-stu-id="5dfce-107">Proposed changes</span></span>

### <a name="november-2020"></a><span data-ttu-id="5dfce-108">2020年11月</span><span class="sxs-lookup"><span data-stu-id="5dfce-108">November 2020</span></span>

<span data-ttu-id="5dfce-109">**> servicenow を共有** することによって、セキュリティで保護されたスコアで servicenow チケットを作成する機能を削除します。</span><span class="sxs-lookup"><span data-stu-id="5dfce-109">Removing the ability to create ServiceNow tickets through Secure Score by going to **Share > ServiceNow** .</span></span>

- <span data-ttu-id="5dfce-110">ServiceNow コネクタのプレビュー期間が終了します。</span><span class="sxs-lookup"><span data-stu-id="5dfce-110">The preview period for the ServiceNow connector is ending.</span></span> <span data-ttu-id="5dfce-111">この機能は2020の終わりまでは利用できなくなります。</span><span class="sxs-lookup"><span data-stu-id="5dfce-111">This capability will no longer available by the end of 2020.</span></span> <span data-ttu-id="5dfce-112">フィードバックをお寄せいただきありがとうございます。次の手順を決定しています。</span><span class="sxs-lookup"><span data-stu-id="5dfce-112">Thank you for your feedback and continued support while we determine next steps.</span></span>

<span data-ttu-id="5dfce-113">エンドポイントの Microsoft Defender (以前の Microsoft Defender ATP) に関連する18の改善アクションを追加します。</span><span class="sxs-lookup"><span data-stu-id="5dfce-113">Adding 18 improvement actions related to Microsoft Defender for Endpoint (previously Microsoft Defender ATP):</span></span>

<span data-ttu-id="5dfce-114">Attack Surface Reduction (ASR) 関連の推奨事項:</span><span class="sxs-lookup"><span data-stu-id="5dfce-114">Attack Surface Reduction (ASR) related recommendations:</span></span>
- <span data-ttu-id="5dfce-115">電子メールクライアントおよび webmail からの実行可能ファイルのコンテンツをブロックする</span><span class="sxs-lookup"><span data-stu-id="5dfce-115">Block executable content from email client and webmail</span></span>
- <span data-ttu-id="5dfce-116">すべての Office アプリケーションで子プロセスを作成することを禁止する</span><span class="sxs-lookup"><span data-stu-id="5dfce-116">Block all Office applications from creating child processes</span></span>
- <span data-ttu-id="5dfce-117">Office アプリケーションで実行可能なコンテンツを作成することを禁止する</span><span class="sxs-lookup"><span data-stu-id="5dfce-117">Block Office applications from creating executable content</span></span>
- <span data-ttu-id="5dfce-118">Office アプリケーションが他のプロセスにコードを挿入するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="5dfce-118">Block Office applications from injecting code into other processes</span></span>
- <span data-ttu-id="5dfce-119">JavaScript または VBScript がダウンロードされた実行可能コンテンツを起動するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="5dfce-119">Block JavaScript or VBScript from launching downloaded executable content</span></span>
- <span data-ttu-id="5dfce-120">難読化する可能性のあるスクリプトの実行をブロックする</span><span class="sxs-lookup"><span data-stu-id="5dfce-120">Block execution of potentially obfuscated scripts</span></span>
- <span data-ttu-id="5dfce-121">Office マクロからの Win32 API 呼び出しをブロックする</span><span class="sxs-lookup"><span data-stu-id="5dfce-121">Block Win32 API calls from Office macros</span></span>
- <span data-ttu-id="5dfce-122">実行可能ファイルが、流行、年齢、または信頼できるリストの条件を満たしていない限り、実行を禁止する</span><span class="sxs-lookup"><span data-stu-id="5dfce-122">Block executable files from running unless they meet a prevalence, age, or trusted list criterion</span></span>
- <span data-ttu-id="5dfce-123">ランサムウェアに対する高度な保護の使用</span><span class="sxs-lookup"><span data-stu-id="5dfce-123">Use advanced protection against ransomware</span></span>
- <span data-ttu-id="5dfce-124">Windows ローカルセキュリティ機関サブシステムからの資格情報の盗用をブロックする (lsass.exe)</span><span class="sxs-lookup"><span data-stu-id="5dfce-124">Block credential stealing from the Windows local security authority subsystem (lsass.exe)</span></span>
- <span data-ttu-id="5dfce-125">PSExec および WMI コマンドからのプロセス作成をブロックする</span><span class="sxs-lookup"><span data-stu-id="5dfce-125">Block process creations originating from PSExec and WMI commands</span></span>
- <span data-ttu-id="5dfce-126">USB から実行される信頼できないおよび署名されていないプロセスをブロックする</span><span class="sxs-lookup"><span data-stu-id="5dfce-126">Block untrusted and unsigned processes that run from USB</span></span>
- <span data-ttu-id="5dfce-127">Office コミュニケーションアプリケーションによる子プロセスの作成を禁止する</span><span class="sxs-lookup"><span data-stu-id="5dfce-127">Block Office communication application from creating child processes</span></span>
- <span data-ttu-id="5dfce-128">Adobe Reader が子プロセスを作成するのをブロックする</span><span class="sxs-lookup"><span data-stu-id="5dfce-128">Block Adobe Reader from creating child processes</span></span>
- <span data-ttu-id="5dfce-129">WMI イベントサブスクリプション経由の永続化をブロックする</span><span class="sxs-lookup"><span data-stu-id="5dfce-129">Block persistence through WMI event subscription</span></span>

<span data-ttu-id="5dfce-130">サービス関連の推奨事項:</span><span class="sxs-lookup"><span data-stu-id="5dfce-130">Services related recommendations:</span></span>
- <span data-ttu-id="5dfce-131">Windows サービスの引用符で囲まれるサービスパスを修正する</span><span class="sxs-lookup"><span data-stu-id="5dfce-131">Fix unquoted service path for Windows services</span></span>
- <span data-ttu-id="5dfce-132">サービスの実行可能パスを共通の保護された場所に変更する</span><span class="sxs-lookup"><span data-stu-id="5dfce-132">Change service executable path to a common protected location</span></span>
- <span data-ttu-id="5dfce-133">Windows レジストリでパスワードがキャッシュされないようにサービスアカウントを変更する</span><span class="sxs-lookup"><span data-stu-id="5dfce-133">Change service account to avoid cached password in windows registry</span></span>

## <a name="related-resources"></a><span data-ttu-id="5dfce-134">関連リソース</span><span class="sxs-lookup"><span data-stu-id="5dfce-134">Related resources</span></span>

- [<span data-ttu-id="5dfce-135">Microsoft セキュリティスコアの概要</span><span class="sxs-lookup"><span data-stu-id="5dfce-135">Microsoft Secure Score overview</span></span>](microsoft-secure-score.md)
- [<span data-ttu-id="5dfce-136">セキュリティ体制にアクセス</span><span class="sxs-lookup"><span data-stu-id="5dfce-136">Assess your security posture</span></span>](microsoft-secure-score-improvement-actions.md)
- [<span data-ttu-id="5dfce-137">Microsoft のセキュリティで保護されたスコア履歴を追跡し、目標を達成する</span><span class="sxs-lookup"><span data-stu-id="5dfce-137">Track your Microsoft Secure Score history and meet goals</span></span>](microsoft-secure-score-history-metrics-trends.md)
- [<span data-ttu-id="5dfce-138">新機能</span><span class="sxs-lookup"><span data-stu-id="5dfce-138">What's new</span></span>](microsoft-secure-score-whats-new.md)
