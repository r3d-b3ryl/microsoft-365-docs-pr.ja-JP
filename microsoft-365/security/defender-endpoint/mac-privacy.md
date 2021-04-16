---
title: Microsoft Defender for Endpoint for Mac のプライバシー
description: プライバシーの制御、プライバシーに影響を与えるポリシー設定を構成する方法、および Microsoft Defender for Endpoint for Mac で収集された診断データに関する情報。
keywords: microsoft、Defender、atp、mac、プライバシー、診断
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 26ae83dc8a8b3bb7d686e3674437a12999b5146f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862237"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="6b708-104">macOS 上のエンドポイント用 Microsoft Defender のプライバシー</span><span class="sxs-lookup"><span data-stu-id="6b708-104">Privacy for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6b708-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="6b708-105">**Applies to:**</span></span>
- [<span data-ttu-id="6b708-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6b708-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6b708-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6b708-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6b708-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="6b708-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6b708-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="6b708-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="6b708-110">Microsoft は、macOS で Microsoft Defender for Endpoint を使用する場合に、データの収集方法と使用方法について選択する必要がある情報とコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="6b708-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="6b708-111">このトピックでは、製品内で使用できるプライバシーコントロール、ポリシー設定を使用してこれらのコントロールを管理する方法、および収集されるデータ イベントの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b708-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="6b708-112">macOS 上の Microsoft Defender for Endpoint のプライバシー制御の概要</span><span class="sxs-lookup"><span data-stu-id="6b708-112">Overview of privacy controls in Microsoft Defender for Endpoint on macOS</span></span>

<span data-ttu-id="6b708-113">このセクションでは、Microsoft Defender for Endpoint on macOS で収集されるさまざまな種類のデータのプライバシー制御について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b708-113">This section describes the privacy controls for the different types of data collected by Microsoft Defender for Endpoint on macOS.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="6b708-114">診断ログ</span><span class="sxs-lookup"><span data-stu-id="6b708-114">Diagnostic data</span></span>

<span data-ttu-id="6b708-115">診断データは、Microsoft Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b708-115">Diagnostic data is used to keep Microsoft Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="6b708-116">診断データには、必須のものとオプションのものがあります。</span><span class="sxs-lookup"><span data-stu-id="6b708-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="6b708-117">組織のポリシー設定などのプライバシー コントロールを使用することで、必須の診断データとオプションの診断データのどちらを Microsoft に送信するかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="6b708-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="6b708-118">Microsoft Defender for Endpoint クライアント ソフトウェアの診断データには、次の 2 つのレベルから選択できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-118">There are two levels of diagnostic data for Microsoft Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="6b708-119">**必須**: Microsoft Defender for Endpoint をセキュリティで保護し、最新の状態に保ち、インストールされているデバイスで期待通り実行するために必要な最小データ。</span><span class="sxs-lookup"><span data-stu-id="6b708-119">**Required**: The minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="6b708-120">**オプション**: Microsoft が製品の改善を行い、問題の検出、診断、修復に役立つ拡張情報を提供する追加データ。</span><span class="sxs-lookup"><span data-stu-id="6b708-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="6b708-121">既定では、必要な診断データだけが Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="6b708-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="6b708-122">クラウドによって提供される保護データ</span><span class="sxs-lookup"><span data-stu-id="6b708-122">Cloud delivered protection data</span></span>

<span data-ttu-id="6b708-123">クラウドによって提供される保護は、クラウド内の最新の保護データへのアクセスを強化し、より速く保護するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b708-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="6b708-124">クラウド配信保護サービスの有効化はオプションですが、エンドポイントやネットワーク全体のマルウェアに対する重要な保護を提供しますので、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="6b708-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="6b708-125">サンプル データ</span><span class="sxs-lookup"><span data-stu-id="6b708-125">Sample data</span></span>

<span data-ttu-id="6b708-126">サンプル データは、Microsoft の疑わしいサンプルを送信して分析することで、製品の保護機能を向上させるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="6b708-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="6b708-127">自動サンプル送信を有効に設定する方法はオプションです。</span><span class="sxs-lookup"><span data-stu-id="6b708-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="6b708-128">この機能が有効で、収集されるサンプルに個人情報が含まれている可能性がある場合は、ユーザーに同意を求めるメッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b708-128">When this feature is enabled and the sample that is collected is likely to contain personal information, the user is prompted for consent.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="6b708-129">ポリシーの設定でプライバシー コントロールを管理します</span><span class="sxs-lookup"><span data-stu-id="6b708-129">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="6b708-130">IT 管理者の場合は、エンタープライズ レベルでこれらのコントロールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-130">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="6b708-131">前のセクションで説明したさまざまな種類のデータのプライバシー制御については、「MacOS での Microsoft Defender for Endpoint の基本設定の設定」 [で詳しく説明します](mac-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="6b708-131">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>

<span data-ttu-id="6b708-132">新しいポリシー設定と同様に、組織でポリシー設定を広く実装する前に、構成する設定が望ましい効果を得られるか確認するために、制限された制御された環境で慎重にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="6b708-132">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="6b708-133">診断データ イベント</span><span class="sxs-lookup"><span data-stu-id="6b708-133">Diagnostic data events</span></span>

<span data-ttu-id="6b708-134">このセクションでは、必要な診断データと見なされる内容、オプションの診断データと見なされる内容、および収集されるイベントとフィールドの説明について説明します。</span><span class="sxs-lookup"><span data-stu-id="6b708-134">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="6b708-135">すべてのイベントで一般的なデータ フィールド</span><span class="sxs-lookup"><span data-stu-id="6b708-135">Data fields that are common for all events</span></span>
<span data-ttu-id="6b708-136">カテゴリやデータ サブタイプに関係なく、すべてのイベントに共通するイベントに関する情報があります。</span><span class="sxs-lookup"><span data-stu-id="6b708-136">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="6b708-137">次のフィールドは、すべてのイベントで一般的と見なされます。</span><span class="sxs-lookup"><span data-stu-id="6b708-137">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="6b708-138">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-138">Field</span></span>                   | <span data-ttu-id="6b708-139">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-139">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="6b708-140">platform</span><span class="sxs-lookup"><span data-stu-id="6b708-140">platform</span></span>                | <span data-ttu-id="6b708-141">アプリが実行されているプラットフォームの広範な分類。</span><span class="sxs-lookup"><span data-stu-id="6b708-141">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="6b708-142">Microsoft は、問題が発生している可能性のあるプラットフォームを特定して、問題の優先順位を正しく設定できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-142">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="6b708-143">machine_guid</span><span class="sxs-lookup"><span data-stu-id="6b708-143">machine_guid</span></span>            | <span data-ttu-id="6b708-144">デバイスに関連付けられている一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6b708-144">Unique identifier associated with the device.</span></span> <span data-ttu-id="6b708-145">Microsoft は、問題がインストールの選択セットに影響を与えるかどうか、および影響を受け取るユーザーの数を特定できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-145">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="6b708-146">sense_guid</span><span class="sxs-lookup"><span data-stu-id="6b708-146">sense_guid</span></span>              | <span data-ttu-id="6b708-147">デバイスに関連付けられている一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6b708-147">Unique identifier associated with the device.</span></span> <span data-ttu-id="6b708-148">Microsoft は、問題がインストールの選択セットに影響を与えるかどうか、および影響を受け取るユーザーの数を特定できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-148">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="6b708-149">org_id</span><span class="sxs-lookup"><span data-stu-id="6b708-149">org_id</span></span>                  | <span data-ttu-id="6b708-150">デバイスが属する企業に関連付けられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6b708-150">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="6b708-151">Microsoft は、問題が一部の企業に影響を与えるかどうか、および影響を受け取る企業の数を特定できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-151">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="6b708-152">ホスト名</span><span class="sxs-lookup"><span data-stu-id="6b708-152">hostname</span></span>                | <span data-ttu-id="6b708-153">ローカル デバイス名 (DNS サフィックスなし)。</span><span class="sxs-lookup"><span data-stu-id="6b708-153">Local device name (without DNS suffix).</span></span> <span data-ttu-id="6b708-154">Microsoft は、問題がインストールの選択セットに影響を与えるかどうか、および影響を受け取るユーザーの数を特定できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-154">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="6b708-155">product_guid</span><span class="sxs-lookup"><span data-stu-id="6b708-155">product_guid</span></span>            | <span data-ttu-id="6b708-156">製品の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6b708-156">Unique identifier of the product.</span></span> <span data-ttu-id="6b708-157">Microsoft は、製品の異なる味に影響を与える問題を区別できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-157">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="6b708-158">app_version</span><span class="sxs-lookup"><span data-stu-id="6b708-158">app_version</span></span>             | <span data-ttu-id="6b708-159">macOS アプリケーションの Microsoft Defender for Endpoint のバージョン。</span><span class="sxs-lookup"><span data-stu-id="6b708-159">Version of the Microsoft Defender for Endpoint on macOS application.</span></span> <span data-ttu-id="6b708-160">Microsoft は、問題を表示している製品のバージョンを特定して、問題の優先順位を正しく設定できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-160">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="6b708-161">sig_version</span><span class="sxs-lookup"><span data-stu-id="6b708-161">sig_version</span></span>             | <span data-ttu-id="6b708-162">セキュリティ インテリジェンス データベースのバージョン。</span><span class="sxs-lookup"><span data-stu-id="6b708-162">Version of security intelligence database.</span></span> <span data-ttu-id="6b708-163">Microsoft が問題を表示しているセキュリティ インテリジェンスのバージョンを特定して、問題を正しく優先順位付けできます。</span><span class="sxs-lookup"><span data-stu-id="6b708-163">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="6b708-164">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="6b708-164">supported_compressions</span></span>  | <span data-ttu-id="6b708-165">アプリケーションでサポートされている圧縮アルゴリズムの一覧 (例 `['gzip']` : .</span><span class="sxs-lookup"><span data-stu-id="6b708-165">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="6b708-166">Microsoft は、アプリケーションと通信するときに使用できる圧縮の種類を理解できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-166">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="6b708-167">release_ring</span><span class="sxs-lookup"><span data-stu-id="6b708-167">release_ring</span></span>            | <span data-ttu-id="6b708-168">デバイスが関連付けられているリング (Insider Fast、Insider Slow、Production など)。</span><span class="sxs-lookup"><span data-stu-id="6b708-168">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="6b708-169">Microsoft は、問題が発生している可能性のあるリリース リングを特定して、問題の優先順位を正しく設定できます。</span><span class="sxs-lookup"><span data-stu-id="6b708-169">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |


### <a name="required-diagnostic-data"></a><span data-ttu-id="6b708-170">必須診断データ</span><span class="sxs-lookup"><span data-stu-id="6b708-170">Required diagnostic data</span></span>

<span data-ttu-id="6b708-171">**必要な診断データ** は、Microsoft Defender for Endpoint をセキュリティで保護し、最新の状態に保ち、インストールされているデバイスで期待した通り実行するために必要な最小データです。</span><span class="sxs-lookup"><span data-stu-id="6b708-171">**Required diagnostic data** is the minimum data necessary to help keep Microsoft Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="6b708-172">必要な診断データは、デバイスまたはソフトウェア構成に関連する可能性がある Microsoft Defender for Endpoint の問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6b708-172">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="6b708-173">たとえば、特定のオペレーティング システム バージョンで Microsoft Defender for Endpoint 機能がクラッシュする頻度が高い場合、新しく導入された機能、または特定の Microsoft Defender for Endpoint 機能が無効になっているかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6b708-173">For example, it can help determine if a Microsoft Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Microsoft Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="6b708-174">必要な診断データは、Microsoft がこれらの問題の検出、診断、および修正を迅速に行い、ユーザーや組織への影響を軽減するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="6b708-174">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="6b708-175">ソフトウェアのセットアップと在庫データ イベント</span><span class="sxs-lookup"><span data-stu-id="6b708-175">Software setup and inventory data events</span></span>

<span data-ttu-id="6b708-176">**Microsoft Defender for Endpoint のインストール/アンインストール**</span><span class="sxs-lookup"><span data-stu-id="6b708-176">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="6b708-177">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b708-177">The following fields are collected:</span></span>

| <span data-ttu-id="6b708-178">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-178">Field</span></span>            | <span data-ttu-id="6b708-179">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-179">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="6b708-180">correlation_id</span><span class="sxs-lookup"><span data-stu-id="6b708-180">correlation_id</span></span>   | <span data-ttu-id="6b708-181">インストールに関連付けられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6b708-181">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="6b708-182">version</span><span class="sxs-lookup"><span data-stu-id="6b708-182">version</span></span>          | <span data-ttu-id="6b708-183">パッケージのバージョン。</span><span class="sxs-lookup"><span data-stu-id="6b708-183">Version of the package.</span></span> |
| <span data-ttu-id="6b708-184">severity</span><span class="sxs-lookup"><span data-stu-id="6b708-184">severity</span></span>         | <span data-ttu-id="6b708-185">メッセージの重大度 (Informational など)。</span><span class="sxs-lookup"><span data-stu-id="6b708-185">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="6b708-186">code</span><span class="sxs-lookup"><span data-stu-id="6b708-186">code</span></span>             | <span data-ttu-id="6b708-187">操作を説明するコード。</span><span class="sxs-lookup"><span data-stu-id="6b708-187">Code that describes the operation.</span></span> |
| <span data-ttu-id="6b708-188">テキスト</span><span class="sxs-lookup"><span data-stu-id="6b708-188">text</span></span>             | <span data-ttu-id="6b708-189">製品のインストールに関連する追加情報。</span><span class="sxs-lookup"><span data-stu-id="6b708-189">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="6b708-190">**Microsoft Defender for Endpoint の構成**</span><span class="sxs-lookup"><span data-stu-id="6b708-190">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="6b708-191">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b708-191">The following fields are collected:</span></span>

| <span data-ttu-id="6b708-192">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-192">Field</span></span>                                               | <span data-ttu-id="6b708-193">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-193">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="6b708-194">antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="6b708-194">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="6b708-195">デバイスでリアルタイム保護が有効になっているかどうか。</span><span class="sxs-lookup"><span data-stu-id="6b708-195">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="6b708-196">antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="6b708-196">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="6b708-197">デバイスでパッシブ モードが有効になっているかどうか。</span><span class="sxs-lookup"><span data-stu-id="6b708-197">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="6b708-198">cloud_service.enabled</span><span class="sxs-lookup"><span data-stu-id="6b708-198">cloud_service.enabled</span></span>                               | <span data-ttu-id="6b708-199">クラウドによって提供される保護がデバイスで有効になっているかどうか。</span><span class="sxs-lookup"><span data-stu-id="6b708-199">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="6b708-200">cloud_service.timeout</span><span class="sxs-lookup"><span data-stu-id="6b708-200">cloud_service.timeout</span></span>                               | <span data-ttu-id="6b708-201">アプリケーションが Microsoft Defender for Endpoint クラウドと通信する際のタイム アウト。</span><span class="sxs-lookup"><span data-stu-id="6b708-201">Time out when the application communicates with the Microsoft Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="6b708-202">cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="6b708-202">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="6b708-203">製品がクラウドに送信する連続ハートビートの間隔。</span><span class="sxs-lookup"><span data-stu-id="6b708-203">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="6b708-204">cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="6b708-204">cloud_service.service_uri</span></span>                           | <span data-ttu-id="6b708-205">クラウドとの通信に使用される URI。</span><span class="sxs-lookup"><span data-stu-id="6b708-205">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="6b708-206">cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="6b708-206">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="6b708-207">デバイスの診断レベル (必須、省略可能)。</span><span class="sxs-lookup"><span data-stu-id="6b708-207">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="6b708-208">cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="6b708-208">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="6b708-209">自動サンプル提出を有効にするかどうか。</span><span class="sxs-lookup"><span data-stu-id="6b708-209">Whether automatic sample submission is turned on or not.</span></span> |
| <span data-ttu-id="6b708-210">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="6b708-210">edr.early_preview</span></span>                                   | <span data-ttu-id="6b708-211">デバイスで EDR 早期プレビュー機能を実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b708-211">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="6b708-212">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="6b708-212">edr.group_id</span></span>                                        | <span data-ttu-id="6b708-213">検出および応答コンポーネントで使用されるグループ識別子。</span><span class="sxs-lookup"><span data-stu-id="6b708-213">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="6b708-214">edr.tags</span><span class="sxs-lookup"><span data-stu-id="6b708-214">edr.tags</span></span>                                            | <span data-ttu-id="6b708-215">ユーザー定義のタグ。</span><span class="sxs-lookup"><span data-stu-id="6b708-215">User-defined tags.</span></span> |
| <span data-ttu-id="6b708-216">機能。 \[オプションの機能名\]</span><span class="sxs-lookup"><span data-stu-id="6b708-216">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="6b708-217">プレビュー機能の一覧と、機能が有効かどうか。</span><span class="sxs-lookup"><span data-stu-id="6b708-217">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="6b708-218">製品とサービスの利用状況データ イベント</span><span class="sxs-lookup"><span data-stu-id="6b708-218">Product and service usage data events</span></span>

<span data-ttu-id="6b708-219">**セキュリティ インテリジェンス更新レポート**</span><span class="sxs-lookup"><span data-stu-id="6b708-219">**Security intelligence update report**</span></span>

<span data-ttu-id="6b708-220">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b708-220">The following fields are collected:</span></span>

| <span data-ttu-id="6b708-221">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-221">Field</span></span>            | <span data-ttu-id="6b708-222">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-222">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="6b708-223">from_version</span><span class="sxs-lookup"><span data-stu-id="6b708-223">from_version</span></span>     | <span data-ttu-id="6b708-224">元のセキュリティ インテリジェンスバージョン。</span><span class="sxs-lookup"><span data-stu-id="6b708-224">Original security intelligence version.</span></span> |
| <span data-ttu-id="6b708-225">to_version</span><span class="sxs-lookup"><span data-stu-id="6b708-225">to_version</span></span>       | <span data-ttu-id="6b708-226">新しいセキュリティ インテリジェンスのバージョン。</span><span class="sxs-lookup"><span data-stu-id="6b708-226">New security intelligence version.</span></span> |
| <span data-ttu-id="6b708-227">status</span><span class="sxs-lookup"><span data-stu-id="6b708-227">status</span></span>           | <span data-ttu-id="6b708-228">成功または失敗を示す更新プログラムの状態。</span><span class="sxs-lookup"><span data-stu-id="6b708-228">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="6b708-229">using_proxy</span><span class="sxs-lookup"><span data-stu-id="6b708-229">using_proxy</span></span>      | <span data-ttu-id="6b708-230">プロキシを使用して更新が行われたかどうか。</span><span class="sxs-lookup"><span data-stu-id="6b708-230">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="6b708-231">error</span><span class="sxs-lookup"><span data-stu-id="6b708-231">error</span></span>            | <span data-ttu-id="6b708-232">更新に失敗した場合のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="6b708-232">Error code if the update failed.</span></span> |
| <span data-ttu-id="6b708-233">理由</span><span class="sxs-lookup"><span data-stu-id="6b708-233">reason</span></span>           | <span data-ttu-id="6b708-234">更新されたファイルが送信された場合にエラー メッセージが表示されます。</span><span class="sxs-lookup"><span data-stu-id="6b708-234">Error message if the updated filed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="6b708-235">製品とサービスのパフォーマンス データ イベント</span><span class="sxs-lookup"><span data-stu-id="6b708-235">Product and service performance data events</span></span>

<span data-ttu-id="6b708-236">**原因不明のアプリケーションの終了 (クラッシュ)**</span><span class="sxs-lookup"><span data-stu-id="6b708-236">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="6b708-237">アプリケーションが予期せず終了した場合のシステム情報とアプリケーションの状態を収集します。</span><span class="sxs-lookup"><span data-stu-id="6b708-237">Collects system information and the state of an application when an application unexpectedly exits.</span></span>

<span data-ttu-id="6b708-238">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b708-238">The following fields are collected:</span></span>

| <span data-ttu-id="6b708-239">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-239">Field</span></span>                          | <span data-ttu-id="6b708-240">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-240">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="6b708-241">v1_crash_count</span><span class="sxs-lookup"><span data-stu-id="6b708-241">v1_crash_count</span></span>                 | <span data-ttu-id="6b708-242">クライアント コンピューターで V1 エンジン プロセスが 1 時間ごとにクラッシュした回数</span><span class="sxs-lookup"><span data-stu-id="6b708-242">Number of times V1 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="6b708-243">v2_crash_count</span><span class="sxs-lookup"><span data-stu-id="6b708-243">v2_crash_count</span></span>                 | <span data-ttu-id="6b708-244">クライアント コンピューターで V2 エンジン プロセスが 1 時間ごとにクラッシュした回数</span><span class="sxs-lookup"><span data-stu-id="6b708-244">Number of times V2 engine process crashed every hour on client machine</span></span>  |
| <span data-ttu-id="6b708-245">EDR_crash_count</span><span class="sxs-lookup"><span data-stu-id="6b708-245">EDR_crash_count</span></span>                | <span data-ttu-id="6b708-246">クライアント コンピューターで 1 時間ごとに EDR プロセスがクラッシュした回数</span><span class="sxs-lookup"><span data-stu-id="6b708-246">Number of times EDR process crashed every hour on client machine</span></span>        |

<span data-ttu-id="6b708-247">**カーネル拡張機能の統計情報**</span><span class="sxs-lookup"><span data-stu-id="6b708-247">**Kernel extension statistics**</span></span>

<span data-ttu-id="6b708-248">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b708-248">The following fields are collected:</span></span>

| <span data-ttu-id="6b708-249">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-249">Field</span></span>            | <span data-ttu-id="6b708-250">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-250">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="6b708-251">version</span><span class="sxs-lookup"><span data-stu-id="6b708-251">version</span></span>          | <span data-ttu-id="6b708-252">macOS 上のエンドポイント用 Microsoft Defender のバージョン。</span><span class="sxs-lookup"><span data-stu-id="6b708-252">Version of Microsoft Defender for Endpoint on macOS.</span></span> |
| <span data-ttu-id="6b708-253">instance_id</span><span class="sxs-lookup"><span data-stu-id="6b708-253">instance_id</span></span>      | <span data-ttu-id="6b708-254">カーネル拡張機能の起動時に生成される一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="6b708-254">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="6b708-255">trace_level</span><span class="sxs-lookup"><span data-stu-id="6b708-255">trace_level</span></span>      | <span data-ttu-id="6b708-256">カーネル拡張機能のトレース レベル。</span><span class="sxs-lookup"><span data-stu-id="6b708-256">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="6b708-257">サブシステム</span><span class="sxs-lookup"><span data-stu-id="6b708-257">subsystem</span></span>        | <span data-ttu-id="6b708-258">リアルタイム保護に使用される基になるサブシステム。</span><span class="sxs-lookup"><span data-stu-id="6b708-258">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="6b708-259">ipc.connects</span><span class="sxs-lookup"><span data-stu-id="6b708-259">ipc.connects</span></span>     | <span data-ttu-id="6b708-260">カーネル拡張機能によって受信された接続要求の数。</span><span class="sxs-lookup"><span data-stu-id="6b708-260">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="6b708-261">ipc.rejects</span><span class="sxs-lookup"><span data-stu-id="6b708-261">ipc.rejects</span></span>      | <span data-ttu-id="6b708-262">カーネル拡張機能によって拒否された接続要求の数。</span><span class="sxs-lookup"><span data-stu-id="6b708-262">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="6b708-263">ipc.connected</span><span class="sxs-lookup"><span data-stu-id="6b708-263">ipc.connected</span></span>    | <span data-ttu-id="6b708-264">カーネル拡張機能へのアクティブな接続が確立されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="6b708-264">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="6b708-265">サポート データ</span><span class="sxs-lookup"><span data-stu-id="6b708-265">Support data</span></span>

<span data-ttu-id="6b708-266">**診断ログ**</span><span class="sxs-lookup"><span data-stu-id="6b708-266">**Diagnostic logs**</span></span>

<span data-ttu-id="6b708-267">診断ログは、フィードバック送信機能の一部としてユーザーの同意を得た場合にのみ収集されます。</span><span class="sxs-lookup"><span data-stu-id="6b708-267">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="6b708-268">次のファイルは、サポート ログの一部として収集されます。</span><span class="sxs-lookup"><span data-stu-id="6b708-268">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="6b708-269">*/Library/Logs/Microsoft/mdatp/ の下のすべてのファイル*</span><span class="sxs-lookup"><span data-stu-id="6b708-269">All files under */Library/Logs/Microsoft/mdatp/*</span></span>
- <span data-ttu-id="6b708-270">MacOS 上の Microsoft Defender for Endpoint で作成および使用される */Library/Application Support/Microsoft/Defender/* の下のファイルのサブセット</span><span class="sxs-lookup"><span data-stu-id="6b708-270">Subset of files under */Library/Application Support/Microsoft/Defender/* that are created and used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="6b708-271">MacOS 上の Microsoft Defender for Endpoint で使用される */Library/Managed Preferences* の下のファイルのサブセット</span><span class="sxs-lookup"><span data-stu-id="6b708-271">Subset of files under */Library/Managed Preferences* that are used by Microsoft Defender for Endpoint on macOS</span></span>
- <span data-ttu-id="6b708-272">/Library/Logs/Microsoft/autoupdate.log</span><span class="sxs-lookup"><span data-stu-id="6b708-272">/Library/Logs/Microsoft/autoupdate.log</span></span>
- <span data-ttu-id="6b708-273">$HOME/ライブラリ/基本設定/com.microsoft.autoupdate2.plist</span><span class="sxs-lookup"><span data-stu-id="6b708-273">$HOME/Library/Preferences/com.microsoft.autoupdate2.plist</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="6b708-274">オプションの診断データ</span><span class="sxs-lookup"><span data-stu-id="6b708-274">Optional diagnostic data</span></span>

<span data-ttu-id="6b708-275">**オプションの診断データは** 、Microsoft が製品の改善を行い、問題の検出、診断、修正に役立つ拡張情報を提供する追加データです。</span><span class="sxs-lookup"><span data-stu-id="6b708-275">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="6b708-276">オプションの診断データを送信するよう選択した場合は、必須の診断データも含まれています。</span><span class="sxs-lookup"><span data-stu-id="6b708-276">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="6b708-277">オプションの診断データの例には、製品構成 (デバイスで設定された除外の数など) と製品のパフォーマンス (製品のコンポーネントのパフォーマンスに関する集計メジャー) に関して Microsoft が収集するデータがあります。</span><span class="sxs-lookup"><span data-stu-id="6b708-277">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="6b708-278">ソフトウェアのセットアップと在庫データ イベント</span><span class="sxs-lookup"><span data-stu-id="6b708-278">Software setup and inventory data events</span></span>

<span data-ttu-id="6b708-279">**Microsoft Defender for Endpoint の構成**</span><span class="sxs-lookup"><span data-stu-id="6b708-279">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="6b708-280">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b708-280">The following fields are collected:</span></span>

| <span data-ttu-id="6b708-281">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-281">Field</span></span>                                              | <span data-ttu-id="6b708-282">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-282">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="6b708-283">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="6b708-283">connection_retry_timeout</span></span>                           | <span data-ttu-id="6b708-284">クラウドとの通信時に接続の再試行が時間切れになります。</span><span class="sxs-lookup"><span data-stu-id="6b708-284">Connection retry time out when communication with the cloud.</span></span> |
| <span data-ttu-id="6b708-285">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="6b708-285">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="6b708-286">製品キャッシュのサイズ。</span><span class="sxs-lookup"><span data-stu-id="6b708-286">Size of the product cache.</span></span> |
| <span data-ttu-id="6b708-287">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="6b708-287">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="6b708-288">毎日アップロードされるクラッシュ ログの制限。</span><span class="sxs-lookup"><span data-stu-id="6b708-288">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="6b708-289">antivirus_engine.exclusions[].is_directory</span><span class="sxs-lookup"><span data-stu-id="6b708-289">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="6b708-290">スキャンからの除外がディレクトリかどうか。</span><span class="sxs-lookup"><span data-stu-id="6b708-290">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="6b708-291">antivirus_engine.exclusions[].path</span><span class="sxs-lookup"><span data-stu-id="6b708-291">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="6b708-292">スキャンから除外されたパス。</span><span class="sxs-lookup"><span data-stu-id="6b708-292">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="6b708-293">antivirus_engine.exclusions[].extension</span><span class="sxs-lookup"><span data-stu-id="6b708-293">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="6b708-294">拡張機能はスキャンから除外されます。</span><span class="sxs-lookup"><span data-stu-id="6b708-294">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="6b708-295">antivirus_engine.exclusions[].name</span><span class="sxs-lookup"><span data-stu-id="6b708-295">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="6b708-296">スキャンから除外されたファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="6b708-296">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="6b708-297">antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="6b708-297">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="6b708-298">製品キャッシュのサイズ。</span><span class="sxs-lookup"><span data-stu-id="6b708-298">Size of the product cache.</span></span> |
| <span data-ttu-id="6b708-299">antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="6b708-299">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="6b708-300">スキャンに使用されるスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="6b708-300">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="6b708-301">antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="6b708-301">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="6b708-302">検疫から復元されたファイルが再び検出される前に、タイム アウトします。</span><span class="sxs-lookup"><span data-stu-id="6b708-302">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="6b708-303">filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="6b708-303">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="6b708-304">フル スキャン ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="6b708-304">Full scan directory.</span></span> |
| <span data-ttu-id="6b708-305">filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="6b708-305">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="6b708-306">クイック スキャンで使用されるディレクトリの一覧。</span><span class="sxs-lookup"><span data-stu-id="6b708-306">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="6b708-307">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="6b708-307">edr.latency_mode</span></span>                                   | <span data-ttu-id="6b708-308">検出および応答コンポーネントで使用される待機時間モード。</span><span class="sxs-lookup"><span data-stu-id="6b708-308">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="6b708-309">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="6b708-309">edr.proxy_address</span></span>                                  | <span data-ttu-id="6b708-310">検出および応答コンポーネントで使用されるプロキシ アドレス。</span><span class="sxs-lookup"><span data-stu-id="6b708-310">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="6b708-311">**Microsoft 自動更新の構成**</span><span class="sxs-lookup"><span data-stu-id="6b708-311">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="6b708-312">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b708-312">The following fields are collected:</span></span>

| <span data-ttu-id="6b708-313">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-313">Field</span></span>                       | <span data-ttu-id="6b708-314">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-314">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="6b708-315">how_to_check</span><span class="sxs-lookup"><span data-stu-id="6b708-315">how_to_check</span></span>                | <span data-ttu-id="6b708-316">製品の更新プログラムのチェック方法 (自動または手動など) を決定します。</span><span class="sxs-lookup"><span data-stu-id="6b708-316">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="6b708-317">channel_name</span><span class="sxs-lookup"><span data-stu-id="6b708-317">channel_name</span></span>                | <span data-ttu-id="6b708-318">デバイスに関連付けられているチャネルを更新します。</span><span class="sxs-lookup"><span data-stu-id="6b708-318">Update channel associated with the device.</span></span> |
| <span data-ttu-id="6b708-319">manifest_server</span><span class="sxs-lookup"><span data-stu-id="6b708-319">manifest_server</span></span>             | <span data-ttu-id="6b708-320">更新プログラムのダウンロードに使用されるサーバー。</span><span class="sxs-lookup"><span data-stu-id="6b708-320">Server used for downloading updates.</span></span> |
| <span data-ttu-id="6b708-321">update_cache</span><span class="sxs-lookup"><span data-stu-id="6b708-321">update_cache</span></span>                | <span data-ttu-id="6b708-322">更新プログラムの格納に使用されるキャッシュの場所。</span><span class="sxs-lookup"><span data-stu-id="6b708-322">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="6b708-323">製品とサービスの使用</span><span class="sxs-lookup"><span data-stu-id="6b708-323">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="6b708-324">診断ログのアップロード開始レポート</span><span class="sxs-lookup"><span data-stu-id="6b708-324">Diagnostic log upload started report</span></span>

<span data-ttu-id="6b708-325">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b708-325">The following fields are collected:</span></span>

| <span data-ttu-id="6b708-326">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-326">Field</span></span>            | <span data-ttu-id="6b708-327">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-327">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="6b708-328">sha256</span><span class="sxs-lookup"><span data-stu-id="6b708-328">sha256</span></span>           | <span data-ttu-id="6b708-329">サポート ログの SHA256 識別子。</span><span class="sxs-lookup"><span data-stu-id="6b708-329">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="6b708-330">size</span><span class="sxs-lookup"><span data-stu-id="6b708-330">size</span></span>             | <span data-ttu-id="6b708-331">サポート ログのサイズ。</span><span class="sxs-lookup"><span data-stu-id="6b708-331">Size of the support log.</span></span> |
| <span data-ttu-id="6b708-332">original_path</span><span class="sxs-lookup"><span data-stu-id="6b708-332">original_path</span></span>    | <span data-ttu-id="6b708-333">サポート ログへのパス (常に */Library/Application Support/Microsoft/Defender/wdavdiag/ の下*)。</span><span class="sxs-lookup"><span data-stu-id="6b708-333">Path to the support log (always under */Library/Application Support/Microsoft/Defender/wdavdiag/*).</span></span> |
| <span data-ttu-id="6b708-334">format</span><span class="sxs-lookup"><span data-stu-id="6b708-334">format</span></span>           | <span data-ttu-id="6b708-335">サポート ログの形式。</span><span class="sxs-lookup"><span data-stu-id="6b708-335">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="6b708-336">診断ログのアップロード完了レポート</span><span class="sxs-lookup"><span data-stu-id="6b708-336">Diagnostic log upload completed report</span></span>

<span data-ttu-id="6b708-337">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b708-337">The following fields are collected:</span></span>

| <span data-ttu-id="6b708-338">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-338">Field</span></span>            | <span data-ttu-id="6b708-339">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-339">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="6b708-340">request_id</span><span class="sxs-lookup"><span data-stu-id="6b708-340">request_id</span></span>       | <span data-ttu-id="6b708-341">サポート ログのアップロード要求の相関関係 ID。</span><span class="sxs-lookup"><span data-stu-id="6b708-341">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="6b708-342">sha256</span><span class="sxs-lookup"><span data-stu-id="6b708-342">sha256</span></span>           | <span data-ttu-id="6b708-343">サポート ログの SHA256 識別子。</span><span class="sxs-lookup"><span data-stu-id="6b708-343">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="6b708-344">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="6b708-344">blob_sas_uri</span></span>     | <span data-ttu-id="6b708-345">アプリケーションがサポート ログをアップロードするために使用する URI。</span><span class="sxs-lookup"><span data-stu-id="6b708-345">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="6b708-346">製品とサービスのパフォーマンス データ イベント</span><span class="sxs-lookup"><span data-stu-id="6b708-346">Product and service performance data events</span></span>

<span data-ttu-id="6b708-347">**原因不明のアプリケーションの終了 (クラッシュ)**</span><span class="sxs-lookup"><span data-stu-id="6b708-347">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="6b708-348">原因不明のアプリケーションの終了と発生時のアプリケーションの状態。</span><span class="sxs-lookup"><span data-stu-id="6b708-348">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="6b708-349">**カーネル拡張機能の統計情報**</span><span class="sxs-lookup"><span data-stu-id="6b708-349">**Kernel extension statistics**</span></span>

<span data-ttu-id="6b708-350">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="6b708-350">The following fields are collected:</span></span>

| <span data-ttu-id="6b708-351">Field</span><span class="sxs-lookup"><span data-stu-id="6b708-351">Field</span></span>                          | <span data-ttu-id="6b708-352">説明</span><span class="sxs-lookup"><span data-stu-id="6b708-352">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="6b708-353">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="6b708-353">pkt_ack_timeout</span></span>                | <span data-ttu-id="6b708-354">次のプロパティは、カーネル拡張機能の起動後に発生したイベントの数を表す集計された数値です。</span><span class="sxs-lookup"><span data-stu-id="6b708-354">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="6b708-355">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="6b708-355">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="6b708-356">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="6b708-356">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="6b708-357">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="6b708-357">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="6b708-358">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="6b708-358">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="6b708-359">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="6b708-359">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="6b708-360">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="6b708-360">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="6b708-361">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="6b708-361">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="6b708-362">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="6b708-362">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="6b708-363">ipc.ack.timeout</span><span class="sxs-lookup"><span data-stu-id="6b708-363">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="6b708-364">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="6b708-364">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="6b708-365">ipc.ack.ackd</span><span class="sxs-lookup"><span data-stu-id="6b708-365">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="6b708-366">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="6b708-366">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="6b708-367">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="6b708-367">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="6b708-368">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="6b708-368">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="6b708-369">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="6b708-369">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="6b708-370">ipc.kauth.vnode.mask</span><span class="sxs-lookup"><span data-stu-id="6b708-370">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="6b708-371">ipc.kauth.vnode.read</span><span class="sxs-lookup"><span data-stu-id="6b708-371">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="6b708-372">ipc.kauth.vnode.write</span><span class="sxs-lookup"><span data-stu-id="6b708-372">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="6b708-373">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="6b708-373">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="6b708-374">ipc.kauth.vnode.del</span><span class="sxs-lookup"><span data-stu-id="6b708-374">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="6b708-375">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="6b708-375">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="6b708-376">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="6b708-376">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="6b708-377">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="6b708-377">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="6b708-378">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="6b708-378">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="6b708-379">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="6b708-379">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="6b708-380">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="6b708-380">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="6b708-381">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="6b708-381">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="6b708-382">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="6b708-382">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="6b708-383">ipc.kauth.vnode.create</span><span class="sxs-lookup"><span data-stu-id="6b708-383">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="6b708-384">ipc.kauth.vnode.move</span><span class="sxs-lookup"><span data-stu-id="6b708-384">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="6b708-385">ipc.kauth.vnode.mount</span><span class="sxs-lookup"><span data-stu-id="6b708-385">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="6b708-386">ipc.kauth.vnode.denied</span><span class="sxs-lookup"><span data-stu-id="6b708-386">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="6b708-387">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="6b708-387">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="6b708-388">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="6b708-388">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="6b708-389">ipc.kauth.file_op.mask</span><span class="sxs-lookup"><span data-stu-id="6b708-389">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="6b708-390">ipc.kauth_file_op.open</span><span class="sxs-lookup"><span data-stu-id="6b708-390">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="6b708-391">ipc.kauth.file_op.close</span><span class="sxs-lookup"><span data-stu-id="6b708-391">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="6b708-392">ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="6b708-392">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="6b708-393">ipc.kauth.file_op.move</span><span class="sxs-lookup"><span data-stu-id="6b708-393">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="6b708-394">ipc.kauth.file_op.link</span><span class="sxs-lookup"><span data-stu-id="6b708-394">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="6b708-395">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="6b708-395">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="6b708-396">ipc.kauth.file_op.remove</span><span class="sxs-lookup"><span data-stu-id="6b708-396">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="6b708-397">ipc.kauth.file_op.unmount</span><span class="sxs-lookup"><span data-stu-id="6b708-397">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="6b708-398">ipc.kauth.file_op.fork</span><span class="sxs-lookup"><span data-stu-id="6b708-398">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="6b708-399">ipc.kauth.file_op.create</span><span class="sxs-lookup"><span data-stu-id="6b708-399">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="6b708-400">リソース</span><span class="sxs-lookup"><span data-stu-id="6b708-400">Resources</span></span>

- [<span data-ttu-id="6b708-401">Microsoft におけるプライバシー</span><span class="sxs-lookup"><span data-stu-id="6b708-401">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
