---
title: Microsoft Defender ATP for Linux のプライバシー
description: プライバシーの制御、プライバシーに影響を与えるポリシー設定の構成方法、および Microsoft Defender ATP for Linux で収集された診断データに関する情報。
keywords: microsoft、Defender、atp、Linux、プライバシー、診断
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 34a06a964baa475c5dedd019e40a6e31e44c0dd9
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065732"
---
# <a name="privacy-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="1a42a-104">Microsoft Defender for Endpoint for Linux のプライバシー</span><span class="sxs-lookup"><span data-stu-id="1a42a-104">Privacy for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1a42a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="1a42a-105">**Applies to:**</span></span>
- [<span data-ttu-id="1a42a-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="1a42a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="1a42a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1a42a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1a42a-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="1a42a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1a42a-109">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="1a42a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="1a42a-110">Microsoft は、Defender for Endpoint for Linux を使用する場合に、データの収集方法と使用方法について選択する必要がある情報とコントロールを提供します。</span><span class="sxs-lookup"><span data-stu-id="1a42a-110">Microsoft is committed to providing you with the information and controls you need to make choices about how your data is collected and used when you’re using Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="1a42a-111">このトピックでは、製品内で使用できるプライバシーコントロール、ポリシー設定を使用してこれらのコントロールを管理する方法、および収集されるデータ イベントの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a42a-111">This topic describes the privacy controls available within the product, how to manage these controls with policy settings and more details on the data events that are collected.</span></span>

## <a name="overview-of-privacy-controls-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="1a42a-112">Microsoft Defender for Endpoint for Linux のプライバシーコントロールの概要</span><span class="sxs-lookup"><span data-stu-id="1a42a-112">Overview of privacy controls in Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="1a42a-113">このセクションでは、Defender for Endpoint for Linux によって収集されるさまざまな種類のデータのプライバシー制御について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a42a-113">This section describes the privacy controls for the different types of data collected by Defender for Endpoint for Linux.</span></span>

### <a name="diagnostic-data"></a><span data-ttu-id="1a42a-114">診断ログ</span><span class="sxs-lookup"><span data-stu-id="1a42a-114">Diagnostic data</span></span>

<span data-ttu-id="1a42a-115">診断データは、Defender for Endpoint を安全かつ最新の状態に保ち、問題を検出、診断、修正し、製品の改善を行う場合に使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-115">Diagnostic data is used to keep Defender for Endpoint secure and up-to-date, detect, diagnose and fix problems, and also make product improvements.</span></span>

<span data-ttu-id="1a42a-116">診断データには、必須のものとオプションのものがあります。</span><span class="sxs-lookup"><span data-stu-id="1a42a-116">Some diagnostic data is required, while some diagnostic data is optional.</span></span> <span data-ttu-id="1a42a-117">組織のポリシー設定などのプライバシー コントロールを使用することで、必須の診断データとオプションの診断データのどちらを Microsoft に送信するかを選択することができます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-117">We give you the ability to choose whether to send us required or optional diagnostic data through the use of privacy controls, such as policy settings for organizations.</span></span>

<span data-ttu-id="1a42a-118">Defender for Endpoint クライアント ソフトウェアの診断データには、次の 2 つのレベルから選択できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-118">There are two levels of diagnostic data for Defender for Endpoint client software that you can choose from:</span></span>

* <span data-ttu-id="1a42a-119">**必須**: Defender for Endpoint をセキュリティで保護し、最新の状態に保ち、インストールされているデバイスで期待通り実行するために必要な最小データ。</span><span class="sxs-lookup"><span data-stu-id="1a42a-119">**Required**: The minimum data necessary to help keep Defender for Endpoint secure, up-to-date, and performing as expected on the device it’s installed on.</span></span>

* <span data-ttu-id="1a42a-120">**オプション**: Microsoft が製品の改善を行い、問題の検出、診断、修復に役立つ拡張情報を提供する追加データ。</span><span class="sxs-lookup"><span data-stu-id="1a42a-120">**Optional**: Additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and remediate issues.</span></span>

<span data-ttu-id="1a42a-121">既定では、必要な診断データだけが Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-121">By default, only required diagnostic data is sent to Microsoft.</span></span>

### <a name="cloud-delivered-protection-data"></a><span data-ttu-id="1a42a-122">クラウドによって提供される保護データ</span><span class="sxs-lookup"><span data-stu-id="1a42a-122">Cloud delivered protection data</span></span>

<span data-ttu-id="1a42a-123">クラウドによって提供される保護は、クラウド内の最新の保護データへのアクセスを強化し、より速く保護するために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-123">Cloud delivered protection is used to provide increased and faster protection with access to the latest protection data in the cloud.</span></span>

<span data-ttu-id="1a42a-124">クラウド配信保護サービスの有効化はオプションですが、エンドポイントやネットワーク全体のマルウェアに対する重要な保護を提供しますので、強くお勧めします。</span><span class="sxs-lookup"><span data-stu-id="1a42a-124">Enabling the cloud-delivered protection service is optional, however it is highly recommended because it provides important protection against malware on your endpoints and across your network.</span></span>

### <a name="sample-data"></a><span data-ttu-id="1a42a-125">サンプル データ</span><span class="sxs-lookup"><span data-stu-id="1a42a-125">Sample data</span></span>

<span data-ttu-id="1a42a-126">サンプル データは、Microsoft の疑わしいサンプルを送信して分析することで、製品の保護機能を向上させるために使用されます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-126">Sample data is used to improve the protection capabilities of the product, by sending Microsoft suspicious samples so they can be analyzed.</span></span> <span data-ttu-id="1a42a-127">自動サンプル送信を有効に設定する方法はオプションです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-127">Enabling automatic sample submission is optional.</span></span>

<span data-ttu-id="1a42a-128">サンプル申請を制御するには、次の 3 つのレベルがあります。</span><span class="sxs-lookup"><span data-stu-id="1a42a-128">There are three levels for controlling sample submission:</span></span>

- <span data-ttu-id="1a42a-129">**なし**: 疑わしいサンプルは Microsoft に送信されません。</span><span class="sxs-lookup"><span data-stu-id="1a42a-129">**None**: no suspicious samples are submitted to Microsoft.</span></span>
- <span data-ttu-id="1a42a-130">**安全**: 個人を特定できる情報 (PII) を含む疑わしいサンプルだけが自動的に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-130">**Safe**: only suspicious samples that do not contain personally identifiable information (PII) are submitted automatically.</span></span> <span data-ttu-id="1a42a-131">これは、この設定の既定値です。</span><span class="sxs-lookup"><span data-stu-id="1a42a-131">This is the default value for this setting.</span></span>
- <span data-ttu-id="1a42a-132">**すべて**: すべての疑わしいサンプルが Microsoft に送信されます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-132">**All**: all suspicious samples are submitted to Microsoft.</span></span>

## <a name="manage-privacy-controls-with-policy-settings"></a><span data-ttu-id="1a42a-133">ポリシーの設定でプライバシー コントロールを管理します</span><span class="sxs-lookup"><span data-stu-id="1a42a-133">Manage privacy controls with policy settings</span></span>

<span data-ttu-id="1a42a-134">IT 管理者の場合は、エンタープライズ レベルでこれらのコントロールを構成できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-134">If you're an IT administrator, you might want to configure these controls at the enterprise level.</span></span> 

<span data-ttu-id="1a42a-135">前のセクションで説明した各種データのプライバシー制御については、「Defender for Endpoint for Linux の設定」 [で詳しく説明します](linux-preferences.md)。</span><span class="sxs-lookup"><span data-stu-id="1a42a-135">The privacy controls for the various types of data described in the preceding section are described in detail in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

<span data-ttu-id="1a42a-136">新しいポリシー設定と同様に、組織でポリシー設定を広く実装する前に、構成する設定が望ましい効果を得られるか確認するために、制限された制御された環境で慎重にテストする必要があります。</span><span class="sxs-lookup"><span data-stu-id="1a42a-136">As with any new policy settings, you should carefully test them out in a limited, controlled environment to ensure the settings that you configure have the desired effect before you implement the policy settings more widely in your organization.</span></span>

## <a name="diagnostic-data-events"></a><span data-ttu-id="1a42a-137">診断データ イベント</span><span class="sxs-lookup"><span data-stu-id="1a42a-137">Diagnostic data events</span></span>

<span data-ttu-id="1a42a-138">このセクションでは、必要な診断データと見なされる内容、オプションの診断データと見なされる内容、および収集されるイベントとフィールドの説明について説明します。</span><span class="sxs-lookup"><span data-stu-id="1a42a-138">This section describes what is considered required diagnostic data and what is considered optional diagnostic data, along with a description of the events and fields that are collected.</span></span>

### <a name="data-fields-that-are-common-for-all-events"></a><span data-ttu-id="1a42a-139">すべてのイベントで一般的なデータ フィールド</span><span class="sxs-lookup"><span data-stu-id="1a42a-139">Data fields that are common for all events</span></span>
<span data-ttu-id="1a42a-140">カテゴリやデータ サブタイプに関係なく、すべてのイベントに共通するイベントに関する情報があります。</span><span class="sxs-lookup"><span data-stu-id="1a42a-140">There is some information about events that is common to all events, regardless of category or data subtype.</span></span> 

<span data-ttu-id="1a42a-141">次のフィールドは、すべてのイベントで一般的と見なされます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-141">The following fields are considered common for all events:</span></span>

| <span data-ttu-id="1a42a-142">Field</span><span class="sxs-lookup"><span data-stu-id="1a42a-142">Field</span></span>                   | <span data-ttu-id="1a42a-143">説明</span><span class="sxs-lookup"><span data-stu-id="1a42a-143">Description</span></span> |
| ----------------------- | ----------- |
| <span data-ttu-id="1a42a-144">platform</span><span class="sxs-lookup"><span data-stu-id="1a42a-144">platform</span></span>                | <span data-ttu-id="1a42a-145">アプリが実行されているプラットフォームの広範な分類。</span><span class="sxs-lookup"><span data-stu-id="1a42a-145">The broad classification of the platform on which the app is running.</span></span> <span data-ttu-id="1a42a-146">Microsoft は、問題が発生している可能性のあるプラットフォームを特定して、問題の優先順位を正しく設定できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-146">Allows Microsoft to identify on which platforms an issue may be occurring so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="1a42a-147">machine_guid</span><span class="sxs-lookup"><span data-stu-id="1a42a-147">machine_guid</span></span>            | <span data-ttu-id="1a42a-148">デバイスに関連付けられている一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="1a42a-148">Unique identifier associated with the device.</span></span> <span data-ttu-id="1a42a-149">Microsoft は、問題がインストールの選択セットに影響を与えるかどうか、および影響を受け取るユーザーの数を特定できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-149">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="1a42a-150">sense_guid</span><span class="sxs-lookup"><span data-stu-id="1a42a-150">sense_guid</span></span>              | <span data-ttu-id="1a42a-151">デバイスに関連付けられている一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="1a42a-151">Unique identifier associated with the device.</span></span> <span data-ttu-id="1a42a-152">Microsoft は、問題がインストールの選択セットに影響を与えるかどうか、および影響を受け取るユーザーの数を特定できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-152">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="1a42a-153">org_id</span><span class="sxs-lookup"><span data-stu-id="1a42a-153">org_id</span></span>                  | <span data-ttu-id="1a42a-154">デバイスが属する企業に関連付けられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="1a42a-154">Unique identifier associated with the enterprise that the device belongs to.</span></span> <span data-ttu-id="1a42a-155">Microsoft は、問題が一部の企業に影響を与えるかどうか、および影響を受け取る企業の数を特定できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-155">Allows Microsoft to identify whether issues are impacting a select set of enterprises and how many enterprises are impacted.</span></span> |
| <span data-ttu-id="1a42a-156">ホスト名</span><span class="sxs-lookup"><span data-stu-id="1a42a-156">hostname</span></span>                | <span data-ttu-id="1a42a-157">ローカル デバイス名 (DNS サフィックスなし)。</span><span class="sxs-lookup"><span data-stu-id="1a42a-157">Local device name (without DNS suffix).</span></span> <span data-ttu-id="1a42a-158">Microsoft は、問題がインストールの選択セットに影響を与えるかどうか、および影響を受け取るユーザーの数を特定できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-158">Allows Microsoft to identify whether issues are impacting a select set of installs and how many users are impacted.</span></span> |
| <span data-ttu-id="1a42a-159">product_guid</span><span class="sxs-lookup"><span data-stu-id="1a42a-159">product_guid</span></span>            | <span data-ttu-id="1a42a-160">製品の一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="1a42a-160">Unique identifier of the product.</span></span> <span data-ttu-id="1a42a-161">Microsoft は、製品の異なる味に影響を与える問題を区別できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-161">Allows Microsoft to differentiate issues impacting different flavors of the product.</span></span> |
| <span data-ttu-id="1a42a-162">app_version</span><span class="sxs-lookup"><span data-stu-id="1a42a-162">app_version</span></span>             | <span data-ttu-id="1a42a-163">Defender for Endpoint for Linux アプリケーションのバージョン。</span><span class="sxs-lookup"><span data-stu-id="1a42a-163">Version of the Defender for Endpoint for Linux application.</span></span> <span data-ttu-id="1a42a-164">Microsoft は、問題を表示している製品のバージョンを特定して、問題の優先順位を正しく設定できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-164">Allows Microsoft to identify which versions of the product are showing an issue so that it can correctly be prioritized.</span></span>|
| <span data-ttu-id="1a42a-165">sig_version</span><span class="sxs-lookup"><span data-stu-id="1a42a-165">sig_version</span></span>             | <span data-ttu-id="1a42a-166">セキュリティ インテリジェンス データベースのバージョン。</span><span class="sxs-lookup"><span data-stu-id="1a42a-166">Version of security intelligence database.</span></span> <span data-ttu-id="1a42a-167">Microsoft が問題を表示しているセキュリティ インテリジェンスのバージョンを特定して、問題を正しく優先順位付けできます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-167">Allows Microsoft to identify which versions of the security intelligence are showing an issue so that it can correctly be prioritized.</span></span> |
| <span data-ttu-id="1a42a-168">supported_compressions</span><span class="sxs-lookup"><span data-stu-id="1a42a-168">supported_compressions</span></span>  | <span data-ttu-id="1a42a-169">アプリケーションでサポートされている圧縮アルゴリズムの一覧 (例 `['gzip']` : .</span><span class="sxs-lookup"><span data-stu-id="1a42a-169">List of compression algorithms supported by the application, for example `['gzip']`.</span></span> <span data-ttu-id="1a42a-170">Microsoft は、アプリケーションと通信するときに使用できる圧縮の種類を理解できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-170">Allows Microsoft to understand what types of compressions can be used when it communicates with the application.</span></span> |
| <span data-ttu-id="1a42a-171">release_ring</span><span class="sxs-lookup"><span data-stu-id="1a42a-171">release_ring</span></span>            | <span data-ttu-id="1a42a-172">デバイスが関連付けられているリング (Insider Fast、Insider Slow、Production など)。</span><span class="sxs-lookup"><span data-stu-id="1a42a-172">Ring that the device is associated with (for example Insider Fast, Insider Slow, Production).</span></span> <span data-ttu-id="1a42a-173">Microsoft は、問題が発生している可能性のあるリリース リングを特定して、問題の優先順位を正しく設定できます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-173">Allows Microsoft to identify on which release ring an issue may be occurring so that it can correctly be prioritized.</span></span> |

### <a name="required-diagnostic-data"></a><span data-ttu-id="1a42a-174">必須診断データ</span><span class="sxs-lookup"><span data-stu-id="1a42a-174">Required diagnostic data</span></span>

<span data-ttu-id="1a42a-175">**必須の診断データ** は、Defender for Endpoint をセキュリティで保護し、最新の状態に保ち、インストールされているデバイスで期待した通り実行するために必要な最小データです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-175">**Required diagnostic data** is the minimum data necessary to help keep Defender for Endpoint secure, up-to-date, and perform as expected on the device it’s installed on.</span></span>

<span data-ttu-id="1a42a-176">必要な診断データは、デバイスまたはソフトウェア構成に関連する可能性がある Microsoft Defender for Endpoint の問題を特定するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-176">Required diagnostic data helps to identify problems with Microsoft Defender for Endpoint that may be related to a device or software configuration.</span></span> <span data-ttu-id="1a42a-177">たとえば、特定のオペレーティング システム バージョンで Defender for Endpoint 機能がクラッシュする頻度が高い場合、新しく導入された機能、または特定の Defender for Endpoint 機能が無効になっているかどうかを判断するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-177">For example, it can help determine if a Defender for Endpoint feature crashes more frequently on a particular operating system version, with newly introduced features, or when certain Defender for Endpoint features are disabled.</span></span> <span data-ttu-id="1a42a-178">必要な診断データは、Microsoft がこれらの問題の検出、診断、および修正を迅速に行い、ユーザーや組織への影響を軽減するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-178">Required diagnostic data helps Microsoft detect, diagnose, and fix these problems more quickly so the impact to users or organizations is reduced.</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="1a42a-179">ソフトウェアのセットアップと在庫データ イベント</span><span class="sxs-lookup"><span data-stu-id="1a42a-179">Software setup and inventory data events</span></span>

<span data-ttu-id="1a42a-180">**Microsoft Defender for Endpoint のインストール/アンインストール**</span><span class="sxs-lookup"><span data-stu-id="1a42a-180">**Microsoft Defender for Endpoint installation / uninstallation**</span></span>

<span data-ttu-id="1a42a-181">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-181">The following fields are collected:</span></span>

| <span data-ttu-id="1a42a-182">Field</span><span class="sxs-lookup"><span data-stu-id="1a42a-182">Field</span></span>            | <span data-ttu-id="1a42a-183">説明</span><span class="sxs-lookup"><span data-stu-id="1a42a-183">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="1a42a-184">correlation_id</span><span class="sxs-lookup"><span data-stu-id="1a42a-184">correlation_id</span></span>   | <span data-ttu-id="1a42a-185">インストールに関連付けられた一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="1a42a-185">Unique identifier associated with the installation.</span></span> |
| <span data-ttu-id="1a42a-186">version</span><span class="sxs-lookup"><span data-stu-id="1a42a-186">version</span></span>          | <span data-ttu-id="1a42a-187">パッケージのバージョン。</span><span class="sxs-lookup"><span data-stu-id="1a42a-187">Version of the package.</span></span> |
| <span data-ttu-id="1a42a-188">severity</span><span class="sxs-lookup"><span data-stu-id="1a42a-188">severity</span></span>         | <span data-ttu-id="1a42a-189">メッセージの重大度 (Informational など)。</span><span class="sxs-lookup"><span data-stu-id="1a42a-189">Severity of the message (for example Informational).</span></span> |
| <span data-ttu-id="1a42a-190">code</span><span class="sxs-lookup"><span data-stu-id="1a42a-190">code</span></span>             | <span data-ttu-id="1a42a-191">操作を説明するコード。</span><span class="sxs-lookup"><span data-stu-id="1a42a-191">Code that describes the operation.</span></span> |
| <span data-ttu-id="1a42a-192">テキスト</span><span class="sxs-lookup"><span data-stu-id="1a42a-192">text</span></span>             | <span data-ttu-id="1a42a-193">製品のインストールに関連する追加情報。</span><span class="sxs-lookup"><span data-stu-id="1a42a-193">Additional information associated with the product installation.</span></span> |

<span data-ttu-id="1a42a-194">**Microsoft Defender for Endpoint の構成**</span><span class="sxs-lookup"><span data-stu-id="1a42a-194">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="1a42a-195">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-195">The following fields are collected:</span></span>

| <span data-ttu-id="1a42a-196">Field</span><span class="sxs-lookup"><span data-stu-id="1a42a-196">Field</span></span>                                               | <span data-ttu-id="1a42a-197">説明</span><span class="sxs-lookup"><span data-stu-id="1a42a-197">Description</span></span> |
| --------------------------------------------------- | ----------- |
| <span data-ttu-id="1a42a-198">antivirus_engine.enable_real_time_protection</span><span class="sxs-lookup"><span data-stu-id="1a42a-198">antivirus_engine.enable_real_time_protection</span></span>        | <span data-ttu-id="1a42a-199">デバイスでリアルタイム保護が有効になっているかどうか。</span><span class="sxs-lookup"><span data-stu-id="1a42a-199">Whether real-time protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="1a42a-200">antivirus_engine.passive_mode</span><span class="sxs-lookup"><span data-stu-id="1a42a-200">antivirus_engine.passive_mode</span></span>                       | <span data-ttu-id="1a42a-201">デバイスでパッシブ モードが有効になっているかどうか。</span><span class="sxs-lookup"><span data-stu-id="1a42a-201">Whether passive mode is enabled on the device or not.</span></span> |
| <span data-ttu-id="1a42a-202">cloud_service.enabled</span><span class="sxs-lookup"><span data-stu-id="1a42a-202">cloud_service.enabled</span></span>                               | <span data-ttu-id="1a42a-203">クラウドによって提供される保護がデバイスで有効になっているかどうか。</span><span class="sxs-lookup"><span data-stu-id="1a42a-203">Whether cloud delivered protection is enabled on the device or not.</span></span> |
| <span data-ttu-id="1a42a-204">cloud_service.timeout</span><span class="sxs-lookup"><span data-stu-id="1a42a-204">cloud_service.timeout</span></span>                               | <span data-ttu-id="1a42a-205">アプリケーションが Defender for Endpoint クラウドと通信する際のタイム アウト。</span><span class="sxs-lookup"><span data-stu-id="1a42a-205">Time out when the application communicates with the Defender for Endpoint cloud.</span></span> |
| <span data-ttu-id="1a42a-206">cloud_service.heartbeat_interval</span><span class="sxs-lookup"><span data-stu-id="1a42a-206">cloud_service.heartbeat_interval</span></span>                    | <span data-ttu-id="1a42a-207">製品がクラウドに送信する連続ハートビートの間隔。</span><span class="sxs-lookup"><span data-stu-id="1a42a-207">Interval between consecutive heartbeats sent by the product to the cloud.</span></span> |
| <span data-ttu-id="1a42a-208">cloud_service.service_uri</span><span class="sxs-lookup"><span data-stu-id="1a42a-208">cloud_service.service_uri</span></span>                           | <span data-ttu-id="1a42a-209">クラウドとの通信に使用される URI。</span><span class="sxs-lookup"><span data-stu-id="1a42a-209">URI used to communicate with the cloud.</span></span> |
| <span data-ttu-id="1a42a-210">cloud_service.diagnostic_level</span><span class="sxs-lookup"><span data-stu-id="1a42a-210">cloud_service.diagnostic_level</span></span>                      | <span data-ttu-id="1a42a-211">デバイスの診断レベル (必須、省略可能)。</span><span class="sxs-lookup"><span data-stu-id="1a42a-211">Diagnostic level of the device (required, optional).</span></span> |
| <span data-ttu-id="1a42a-212">cloud_service.automatic_sample_submission</span><span class="sxs-lookup"><span data-stu-id="1a42a-212">cloud_service.automatic_sample_submission</span></span>           | <span data-ttu-id="1a42a-213">デバイスの自動サンプル提出レベル (なし、安全、すべて)。</span><span class="sxs-lookup"><span data-stu-id="1a42a-213">Automatic sample submission level of the device (none, safe, all).</span></span> |
| <span data-ttu-id="1a42a-214">edr.early_preview</span><span class="sxs-lookup"><span data-stu-id="1a42a-214">edr.early_preview</span></span>                                   | <span data-ttu-id="1a42a-215">デバイスで EDR 早期プレビュー機能を実行するかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a42a-215">Whether the device should run EDR early preview features.</span></span> |
| <span data-ttu-id="1a42a-216">edr.group_id</span><span class="sxs-lookup"><span data-stu-id="1a42a-216">edr.group_id</span></span>                                        | <span data-ttu-id="1a42a-217">検出および応答コンポーネントで使用されるグループ識別子。</span><span class="sxs-lookup"><span data-stu-id="1a42a-217">Group identifier used by the detection and response component.</span></span> |
| <span data-ttu-id="1a42a-218">edr.tags</span><span class="sxs-lookup"><span data-stu-id="1a42a-218">edr.tags</span></span>                                            | <span data-ttu-id="1a42a-219">ユーザー定義のタグ。</span><span class="sxs-lookup"><span data-stu-id="1a42a-219">User-defined tags.</span></span> |
| <span data-ttu-id="1a42a-220">機能。 \[オプションの機能名\]</span><span class="sxs-lookup"><span data-stu-id="1a42a-220">features.\[optional feature name\]</span></span>                  | <span data-ttu-id="1a42a-221">プレビュー機能の一覧と、機能が有効かどうか。</span><span class="sxs-lookup"><span data-stu-id="1a42a-221">List of preview features, along with whether they are enabled or not.</span></span> |

#### <a name="product-and-service-usage-data-events"></a><span data-ttu-id="1a42a-222">製品とサービスの利用状況データ イベント</span><span class="sxs-lookup"><span data-stu-id="1a42a-222">Product and service usage data events</span></span>

<span data-ttu-id="1a42a-223">**セキュリティ インテリジェンス更新レポート**</span><span class="sxs-lookup"><span data-stu-id="1a42a-223">**Security intelligence update report**</span></span>

<span data-ttu-id="1a42a-224">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-224">The following fields are collected:</span></span>

| <span data-ttu-id="1a42a-225">Field</span><span class="sxs-lookup"><span data-stu-id="1a42a-225">Field</span></span>            | <span data-ttu-id="1a42a-226">説明</span><span class="sxs-lookup"><span data-stu-id="1a42a-226">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="1a42a-227">from_version</span><span class="sxs-lookup"><span data-stu-id="1a42a-227">from_version</span></span>     | <span data-ttu-id="1a42a-228">元のセキュリティ インテリジェンスバージョン。</span><span class="sxs-lookup"><span data-stu-id="1a42a-228">Original security intelligence version.</span></span> |
| <span data-ttu-id="1a42a-229">to_version</span><span class="sxs-lookup"><span data-stu-id="1a42a-229">to_version</span></span>       | <span data-ttu-id="1a42a-230">新しいセキュリティ インテリジェンスのバージョン。</span><span class="sxs-lookup"><span data-stu-id="1a42a-230">New security intelligence version.</span></span> |
| <span data-ttu-id="1a42a-231">status</span><span class="sxs-lookup"><span data-stu-id="1a42a-231">status</span></span>           | <span data-ttu-id="1a42a-232">成功または失敗を示す更新プログラムの状態。</span><span class="sxs-lookup"><span data-stu-id="1a42a-232">Status of the update indicating success or failure.</span></span> |
| <span data-ttu-id="1a42a-233">using_proxy</span><span class="sxs-lookup"><span data-stu-id="1a42a-233">using_proxy</span></span>      | <span data-ttu-id="1a42a-234">プロキシを使用して更新が行われたかどうか。</span><span class="sxs-lookup"><span data-stu-id="1a42a-234">Whether the update was done over a proxy.</span></span> |
| <span data-ttu-id="1a42a-235">error</span><span class="sxs-lookup"><span data-stu-id="1a42a-235">error</span></span>            | <span data-ttu-id="1a42a-236">更新に失敗した場合のエラー コード。</span><span class="sxs-lookup"><span data-stu-id="1a42a-236">Error code if the update failed.</span></span> |
| <span data-ttu-id="1a42a-237">理由</span><span class="sxs-lookup"><span data-stu-id="1a42a-237">reason</span></span>           | <span data-ttu-id="1a42a-238">更新に失敗した場合のエラー メッセージ。</span><span class="sxs-lookup"><span data-stu-id="1a42a-238">Error message if the update failed.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="1a42a-239">製品とサービスのパフォーマンス データ イベント</span><span class="sxs-lookup"><span data-stu-id="1a42a-239">Product and service performance data events</span></span>

<span data-ttu-id="1a42a-240">**カーネル拡張機能の統計情報**</span><span class="sxs-lookup"><span data-stu-id="1a42a-240">**Kernel extension statistics**</span></span>

<span data-ttu-id="1a42a-241">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-241">The following fields are collected:</span></span>

| <span data-ttu-id="1a42a-242">Field</span><span class="sxs-lookup"><span data-stu-id="1a42a-242">Field</span></span>            | <span data-ttu-id="1a42a-243">説明</span><span class="sxs-lookup"><span data-stu-id="1a42a-243">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="1a42a-244">version</span><span class="sxs-lookup"><span data-stu-id="1a42a-244">version</span></span>          | <span data-ttu-id="1a42a-245">Defender for Endpoint for Linux のバージョン。</span><span class="sxs-lookup"><span data-stu-id="1a42a-245">Version of Defender for Endpoint for Linux.</span></span> |
| <span data-ttu-id="1a42a-246">instance_id</span><span class="sxs-lookup"><span data-stu-id="1a42a-246">instance_id</span></span>      | <span data-ttu-id="1a42a-247">カーネル拡張機能の起動時に生成される一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="1a42a-247">Unique identifier generated on kernel extension startup.</span></span> |
| <span data-ttu-id="1a42a-248">trace_level</span><span class="sxs-lookup"><span data-stu-id="1a42a-248">trace_level</span></span>      | <span data-ttu-id="1a42a-249">カーネル拡張機能のトレース レベル。</span><span class="sxs-lookup"><span data-stu-id="1a42a-249">Trace level of the kernel extension.</span></span> |
| <span data-ttu-id="1a42a-250">サブシステム</span><span class="sxs-lookup"><span data-stu-id="1a42a-250">subsystem</span></span>        | <span data-ttu-id="1a42a-251">リアルタイム保護に使用される基になるサブシステム。</span><span class="sxs-lookup"><span data-stu-id="1a42a-251">The underlying subsystem used for real-time protection.</span></span> |
| <span data-ttu-id="1a42a-252">ipc.connects</span><span class="sxs-lookup"><span data-stu-id="1a42a-252">ipc.connects</span></span>     | <span data-ttu-id="1a42a-253">カーネル拡張機能によって受信された接続要求の数。</span><span class="sxs-lookup"><span data-stu-id="1a42a-253">Number of connection requests received by the kernel extension.</span></span> |
| <span data-ttu-id="1a42a-254">ipc.rejects</span><span class="sxs-lookup"><span data-stu-id="1a42a-254">ipc.rejects</span></span>      | <span data-ttu-id="1a42a-255">カーネル拡張機能によって拒否された接続要求の数。</span><span class="sxs-lookup"><span data-stu-id="1a42a-255">Number of connection requests rejected by the kernel extension.</span></span> |
| <span data-ttu-id="1a42a-256">ipc.connected</span><span class="sxs-lookup"><span data-stu-id="1a42a-256">ipc.connected</span></span>    | <span data-ttu-id="1a42a-257">カーネル拡張機能へのアクティブな接続が確立されているかどうかを指定します。</span><span class="sxs-lookup"><span data-stu-id="1a42a-257">Whether there is any active connection to the kernel extension.</span></span> |

#### <a name="support-data"></a><span data-ttu-id="1a42a-258">サポート データ</span><span class="sxs-lookup"><span data-stu-id="1a42a-258">Support data</span></span>

<span data-ttu-id="1a42a-259">**診断ログ**</span><span class="sxs-lookup"><span data-stu-id="1a42a-259">**Diagnostic logs**</span></span>

<span data-ttu-id="1a42a-260">診断ログは、フィードバック送信機能の一部としてユーザーの同意を得た場合にのみ収集されます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-260">Diagnostic logs are collected only with the consent of the user as part of the feedback submission feature.</span></span> <span data-ttu-id="1a42a-261">次のファイルは、サポート ログの一部として収集されます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-261">The following files are collected as part of the support logs:</span></span>

- <span data-ttu-id="1a42a-262">*/var/log/microsoft/mdatp の下のすべてのファイル*</span><span class="sxs-lookup"><span data-stu-id="1a42a-262">All files under */var/log/microsoft/mdatp*</span></span>
- <span data-ttu-id="1a42a-263">Defender for Endpoint for Linux で作成および使用される */etc/opt/microsoft/mdatp* の下のファイルのサブセット</span><span class="sxs-lookup"><span data-stu-id="1a42a-263">Subset of files under */etc/opt/microsoft/mdatp* that are created and used by Defender for Endpoint for Linux</span></span>
- <span data-ttu-id="1a42a-264">*\* /var/log/microsoft_mdatp_ .log の下の製品のインストールとアンインストール ログ*</span><span class="sxs-lookup"><span data-stu-id="1a42a-264">Product installation and uninstallation logs under */var/log/microsoft_mdatp_\*.log*</span></span>

### <a name="optional-diagnostic-data"></a><span data-ttu-id="1a42a-265">オプションの診断データ</span><span class="sxs-lookup"><span data-stu-id="1a42a-265">Optional diagnostic data</span></span>

<span data-ttu-id="1a42a-266">**オプションの診断データは** 、Microsoft が製品の改善を行い、問題の検出、診断、修正に役立つ拡張情報を提供する追加データです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-266">**Optional diagnostic data** is additional data that helps Microsoft make product improvements and provides enhanced information to help detect, diagnose, and fix issues.</span></span>

<span data-ttu-id="1a42a-267">オプションの診断データを送信するよう選択した場合は、必須の診断データも含まれています。</span><span class="sxs-lookup"><span data-stu-id="1a42a-267">If you choose to send us optional diagnostic data, required diagnostic data is also included.</span></span>

<span data-ttu-id="1a42a-268">オプションの診断データの例には、製品構成 (デバイスで設定された除外の数など) と製品のパフォーマンス (製品のコンポーネントのパフォーマンスに関する集計メジャー) に関して Microsoft が収集するデータがあります。</span><span class="sxs-lookup"><span data-stu-id="1a42a-268">Examples of optional diagnostic data include data Microsoft collects about product configuration (for example number of exclusions set on the device) and product performance (aggregate measures about the performance of components of the product).</span></span>

#### <a name="software-setup-and-inventory-data-events"></a><span data-ttu-id="1a42a-269">ソフトウェアのセットアップと在庫データ イベント</span><span class="sxs-lookup"><span data-stu-id="1a42a-269">Software setup and inventory data events</span></span>

<span data-ttu-id="1a42a-270">**Microsoft Defender for Endpoint の構成**</span><span class="sxs-lookup"><span data-stu-id="1a42a-270">**Microsoft Defender for Endpoint configuration**</span></span>

<span data-ttu-id="1a42a-271">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-271">The following fields are collected:</span></span>

| <span data-ttu-id="1a42a-272">Field</span><span class="sxs-lookup"><span data-stu-id="1a42a-272">Field</span></span>                                              | <span data-ttu-id="1a42a-273">説明</span><span class="sxs-lookup"><span data-stu-id="1a42a-273">Description</span></span> |
| -------------------------------------------------- | ----------- |
| <span data-ttu-id="1a42a-274">connection_retry_timeout</span><span class="sxs-lookup"><span data-stu-id="1a42a-274">connection_retry_timeout</span></span>                           | <span data-ttu-id="1a42a-275">クラウドとの通信時の接続再試行のタイム アウト。</span><span class="sxs-lookup"><span data-stu-id="1a42a-275">Connection retry time-out when communication with the cloud.</span></span> |
| <span data-ttu-id="1a42a-276">file_hash_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="1a42a-276">file_hash_cache_maximum</span></span>                            | <span data-ttu-id="1a42a-277">製品キャッシュのサイズ。</span><span class="sxs-lookup"><span data-stu-id="1a42a-277">Size of the product cache.</span></span> |
| <span data-ttu-id="1a42a-278">crash_upload_daily_limit</span><span class="sxs-lookup"><span data-stu-id="1a42a-278">crash_upload_daily_limit</span></span>                           | <span data-ttu-id="1a42a-279">毎日アップロードされるクラッシュ ログの制限。</span><span class="sxs-lookup"><span data-stu-id="1a42a-279">Limit of crash logs uploaded daily.</span></span> |
| <span data-ttu-id="1a42a-280">antivirus_engine.exclusions[].is_directory</span><span class="sxs-lookup"><span data-stu-id="1a42a-280">antivirus_engine.exclusions[].is_directory</span></span>         | <span data-ttu-id="1a42a-281">スキャンからの除外がディレクトリかどうか。</span><span class="sxs-lookup"><span data-stu-id="1a42a-281">Whether the exclusion from scanning is a directory or not.</span></span> |
| <span data-ttu-id="1a42a-282">antivirus_engine.exclusions[].path</span><span class="sxs-lookup"><span data-stu-id="1a42a-282">antivirus_engine.exclusions[].path</span></span>                 | <span data-ttu-id="1a42a-283">スキャンから除外されたパス。</span><span class="sxs-lookup"><span data-stu-id="1a42a-283">Path that was excluded from scanning.</span></span> |
| <span data-ttu-id="1a42a-284">antivirus_engine.exclusions[].extension</span><span class="sxs-lookup"><span data-stu-id="1a42a-284">antivirus_engine.exclusions[].extension</span></span>            | <span data-ttu-id="1a42a-285">拡張機能はスキャンから除外されます。</span><span class="sxs-lookup"><span data-stu-id="1a42a-285">Extension excluded from scanning.</span></span> |
| <span data-ttu-id="1a42a-286">antivirus_engine.exclusions[].name</span><span class="sxs-lookup"><span data-stu-id="1a42a-286">antivirus_engine.exclusions[].name</span></span>                 | <span data-ttu-id="1a42a-287">スキャンから除外されたファイルの名前。</span><span class="sxs-lookup"><span data-stu-id="1a42a-287">Name of the file excluded from scanning.</span></span> |
| <span data-ttu-id="1a42a-288">antivirus_engine.scan_cache_maximum</span><span class="sxs-lookup"><span data-stu-id="1a42a-288">antivirus_engine.scan_cache_maximum</span></span>                | <span data-ttu-id="1a42a-289">製品キャッシュのサイズ。</span><span class="sxs-lookup"><span data-stu-id="1a42a-289">Size of the product cache.</span></span> |
| <span data-ttu-id="1a42a-290">antivirus_engine.maximum_scan_threads</span><span class="sxs-lookup"><span data-stu-id="1a42a-290">antivirus_engine.maximum_scan_threads</span></span>              | <span data-ttu-id="1a42a-291">スキャンに使用されるスレッドの最大数。</span><span class="sxs-lookup"><span data-stu-id="1a42a-291">Maximum number of threads used for scanning.</span></span> |
| <span data-ttu-id="1a42a-292">antivirus_engine.threat_restoration_exclusion_time</span><span class="sxs-lookup"><span data-stu-id="1a42a-292">antivirus_engine.threat_restoration_exclusion_time</span></span> | <span data-ttu-id="1a42a-293">検疫から復元されたファイルが再び検出される前に、タイム アウトします。</span><span class="sxs-lookup"><span data-stu-id="1a42a-293">Time out before a file restored from the quarantine can be detected again.</span></span> |
| <span data-ttu-id="1a42a-294">filesystem_scanner.full_scan_directory</span><span class="sxs-lookup"><span data-stu-id="1a42a-294">filesystem_scanner.full_scan_directory</span></span>             | <span data-ttu-id="1a42a-295">フル スキャン ディレクトリ。</span><span class="sxs-lookup"><span data-stu-id="1a42a-295">Full scan directory.</span></span> |
| <span data-ttu-id="1a42a-296">filesystem_scanner.quick_scan_directories</span><span class="sxs-lookup"><span data-stu-id="1a42a-296">filesystem_scanner.quick_scan_directories</span></span>          | <span data-ttu-id="1a42a-297">クイック スキャンで使用されるディレクトリの一覧。</span><span class="sxs-lookup"><span data-stu-id="1a42a-297">List of directories used in quick scan.</span></span> |
| <span data-ttu-id="1a42a-298">edr.latency_mode</span><span class="sxs-lookup"><span data-stu-id="1a42a-298">edr.latency_mode</span></span>                                   | <span data-ttu-id="1a42a-299">検出および応答コンポーネントで使用される待機時間モード。</span><span class="sxs-lookup"><span data-stu-id="1a42a-299">Latency mode used by the detection and response component.</span></span> |
| <span data-ttu-id="1a42a-300">edr.proxy_address</span><span class="sxs-lookup"><span data-stu-id="1a42a-300">edr.proxy_address</span></span>                                  | <span data-ttu-id="1a42a-301">検出および応答コンポーネントで使用されるプロキシ アドレス。</span><span class="sxs-lookup"><span data-stu-id="1a42a-301">Proxy address used by the detection and response component.</span></span> |

<span data-ttu-id="1a42a-302">**Microsoft 自動更新の構成**</span><span class="sxs-lookup"><span data-stu-id="1a42a-302">**Microsoft Auto-Update configuration**</span></span>

<span data-ttu-id="1a42a-303">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-303">The following fields are collected:</span></span>

| <span data-ttu-id="1a42a-304">Field</span><span class="sxs-lookup"><span data-stu-id="1a42a-304">Field</span></span>                       | <span data-ttu-id="1a42a-305">説明</span><span class="sxs-lookup"><span data-stu-id="1a42a-305">Description</span></span> |
| --------------------------- | ----------- |
| <span data-ttu-id="1a42a-306">how_to_check</span><span class="sxs-lookup"><span data-stu-id="1a42a-306">how_to_check</span></span>                | <span data-ttu-id="1a42a-307">製品の更新プログラムのチェック方法 (自動または手動など) を決定します。</span><span class="sxs-lookup"><span data-stu-id="1a42a-307">Determines how product updates are checked (for example automatic or manual).</span></span> |
| <span data-ttu-id="1a42a-308">channel_name</span><span class="sxs-lookup"><span data-stu-id="1a42a-308">channel_name</span></span>                | <span data-ttu-id="1a42a-309">デバイスに関連付けられているチャネルを更新します。</span><span class="sxs-lookup"><span data-stu-id="1a42a-309">Update channel associated with the device.</span></span> |
| <span data-ttu-id="1a42a-310">manifest_server</span><span class="sxs-lookup"><span data-stu-id="1a42a-310">manifest_server</span></span>             | <span data-ttu-id="1a42a-311">更新プログラムのダウンロードに使用されるサーバー。</span><span class="sxs-lookup"><span data-stu-id="1a42a-311">Server used for downloading updates.</span></span> |
| <span data-ttu-id="1a42a-312">update_cache</span><span class="sxs-lookup"><span data-stu-id="1a42a-312">update_cache</span></span>                | <span data-ttu-id="1a42a-313">更新プログラムの格納に使用されるキャッシュの場所。</span><span class="sxs-lookup"><span data-stu-id="1a42a-313">Location of the cache used to store updates.</span></span> |

### <a name="product-and-service-usage"></a><span data-ttu-id="1a42a-314">製品とサービスの使用</span><span class="sxs-lookup"><span data-stu-id="1a42a-314">Product and service usage</span></span>

#### <a name="diagnostic-log-upload-started-report"></a><span data-ttu-id="1a42a-315">診断ログのアップロード開始レポート</span><span class="sxs-lookup"><span data-stu-id="1a42a-315">Diagnostic log upload started report</span></span>

<span data-ttu-id="1a42a-316">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-316">The following fields are collected:</span></span>

| <span data-ttu-id="1a42a-317">Field</span><span class="sxs-lookup"><span data-stu-id="1a42a-317">Field</span></span>            | <span data-ttu-id="1a42a-318">説明</span><span class="sxs-lookup"><span data-stu-id="1a42a-318">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="1a42a-319">sha256</span><span class="sxs-lookup"><span data-stu-id="1a42a-319">sha256</span></span>           | <span data-ttu-id="1a42a-320">サポート ログの SHA256 識別子。</span><span class="sxs-lookup"><span data-stu-id="1a42a-320">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="1a42a-321">size</span><span class="sxs-lookup"><span data-stu-id="1a42a-321">size</span></span>             | <span data-ttu-id="1a42a-322">サポート ログのサイズ。</span><span class="sxs-lookup"><span data-stu-id="1a42a-322">Size of the support log.</span></span> |
| <span data-ttu-id="1a42a-323">original_path</span><span class="sxs-lookup"><span data-stu-id="1a42a-323">original_path</span></span>    | <span data-ttu-id="1a42a-324">サポート ログへのパス (常に */var/opt/microsoft/mdatp/wdavdiag/ の下*)。</span><span class="sxs-lookup"><span data-stu-id="1a42a-324">Path to the support log (always under */var/opt/microsoft/mdatp/wdavdiag/*).</span></span> |
| <span data-ttu-id="1a42a-325">format</span><span class="sxs-lookup"><span data-stu-id="1a42a-325">format</span></span>           | <span data-ttu-id="1a42a-326">サポート ログの形式。</span><span class="sxs-lookup"><span data-stu-id="1a42a-326">Format of the support log.</span></span> |

#### <a name="diagnostic-log-upload-completed-report"></a><span data-ttu-id="1a42a-327">診断ログのアップロード完了レポート</span><span class="sxs-lookup"><span data-stu-id="1a42a-327">Diagnostic log upload completed report</span></span>

<span data-ttu-id="1a42a-328">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-328">The following fields are collected:</span></span>

| <span data-ttu-id="1a42a-329">Field</span><span class="sxs-lookup"><span data-stu-id="1a42a-329">Field</span></span>            | <span data-ttu-id="1a42a-330">説明</span><span class="sxs-lookup"><span data-stu-id="1a42a-330">Description</span></span> |
| ---------------- | ----------- |
| <span data-ttu-id="1a42a-331">request_id</span><span class="sxs-lookup"><span data-stu-id="1a42a-331">request_id</span></span>       | <span data-ttu-id="1a42a-332">サポート ログのアップロード要求の相関関係 ID。</span><span class="sxs-lookup"><span data-stu-id="1a42a-332">Correlation ID for the support log upload request.</span></span> |
| <span data-ttu-id="1a42a-333">sha256</span><span class="sxs-lookup"><span data-stu-id="1a42a-333">sha256</span></span>           | <span data-ttu-id="1a42a-334">サポート ログの SHA256 識別子。</span><span class="sxs-lookup"><span data-stu-id="1a42a-334">SHA256 identifier of the support log.</span></span> |
| <span data-ttu-id="1a42a-335">blob_sas_uri</span><span class="sxs-lookup"><span data-stu-id="1a42a-335">blob_sas_uri</span></span>     | <span data-ttu-id="1a42a-336">アプリケーションがサポート ログをアップロードするために使用する URI。</span><span class="sxs-lookup"><span data-stu-id="1a42a-336">URI used by the application to upload the support log.</span></span> |

#### <a name="product-and-service-performance-data-events"></a><span data-ttu-id="1a42a-337">製品とサービスのパフォーマンス データ イベント</span><span class="sxs-lookup"><span data-stu-id="1a42a-337">Product and service performance data events</span></span>

<span data-ttu-id="1a42a-338">**原因不明のアプリケーションの終了 (クラッシュ)**</span><span class="sxs-lookup"><span data-stu-id="1a42a-338">**Unexpected application exit (crash)**</span></span>

<span data-ttu-id="1a42a-339">原因不明のアプリケーションの終了と発生時のアプリケーションの状態。</span><span class="sxs-lookup"><span data-stu-id="1a42a-339">Unexpected application exits and the state of the application when that happens.</span></span>

<span data-ttu-id="1a42a-340">**カーネル拡張機能の統計情報**</span><span class="sxs-lookup"><span data-stu-id="1a42a-340">**Kernel extension statistics**</span></span>

<span data-ttu-id="1a42a-341">収集されるフィールドは、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="1a42a-341">The following fields are collected:</span></span>

| <span data-ttu-id="1a42a-342">Field</span><span class="sxs-lookup"><span data-stu-id="1a42a-342">Field</span></span>                          | <span data-ttu-id="1a42a-343">説明</span><span class="sxs-lookup"><span data-stu-id="1a42a-343">Description</span></span> |
| ------------------------------ | ----------- |
| <span data-ttu-id="1a42a-344">pkt_ack_timeout</span><span class="sxs-lookup"><span data-stu-id="1a42a-344">pkt_ack_timeout</span></span>                | <span data-ttu-id="1a42a-345">次のプロパティは、カーネル拡張機能の起動後に発生したイベントの数を表す集計された数値です。</span><span class="sxs-lookup"><span data-stu-id="1a42a-345">The following properties are aggregated numerical values, representing count of events that happened since kernel extension startup.</span></span> |
| <span data-ttu-id="1a42a-346">pkt_ack_conn_timeout</span><span class="sxs-lookup"><span data-stu-id="1a42a-346">pkt_ack_conn_timeout</span></span>             | |
| <span data-ttu-id="1a42a-347">ipc.ack_pkts</span><span class="sxs-lookup"><span data-stu-id="1a42a-347">ipc.ack_pkts</span></span>                     | |
| <span data-ttu-id="1a42a-348">ipc.nack_pkts</span><span class="sxs-lookup"><span data-stu-id="1a42a-348">ipc.nack_pkts</span></span>                    | |
| <span data-ttu-id="1a42a-349">ipc.send.ack_no_conn</span><span class="sxs-lookup"><span data-stu-id="1a42a-349">ipc.send.ack_no_conn</span></span>             | |
| <span data-ttu-id="1a42a-350">ipc.send.nack_no_conn</span><span class="sxs-lookup"><span data-stu-id="1a42a-350">ipc.send.nack_no_conn</span></span>            | |
| <span data-ttu-id="1a42a-351">ipc.send.ack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="1a42a-351">ipc.send.ack_no_qsq</span></span>              | |
| <span data-ttu-id="1a42a-352">ipc.send.nack_no_qsq</span><span class="sxs-lookup"><span data-stu-id="1a42a-352">ipc.send.nack_no_qsq</span></span>             | |
| <span data-ttu-id="1a42a-353">ipc.ack.no_space</span><span class="sxs-lookup"><span data-stu-id="1a42a-353">ipc.ack.no_space</span></span>                 | |
| <span data-ttu-id="1a42a-354">ipc.ack.timeout</span><span class="sxs-lookup"><span data-stu-id="1a42a-354">ipc.ack.timeout</span></span>                  | |
| <span data-ttu-id="1a42a-355">ipc.ack.ackd_fast</span><span class="sxs-lookup"><span data-stu-id="1a42a-355">ipc.ack.ackd_fast</span></span>                | |
| <span data-ttu-id="1a42a-356">ipc.ack.ackd</span><span class="sxs-lookup"><span data-stu-id="1a42a-356">ipc.ack.ackd</span></span>                     | |
| <span data-ttu-id="1a42a-357">ipc.recv.bad_pkt_len</span><span class="sxs-lookup"><span data-stu-id="1a42a-357">ipc.recv.bad_pkt_len</span></span>             | |
| <span data-ttu-id="1a42a-358">ipc.recv.bad_reply_len</span><span class="sxs-lookup"><span data-stu-id="1a42a-358">ipc.recv.bad_reply_len</span></span>           | |
| <span data-ttu-id="1a42a-359">ipc.recv.no_waiter</span><span class="sxs-lookup"><span data-stu-id="1a42a-359">ipc.recv.no_waiter</span></span>               | |
| <span data-ttu-id="1a42a-360">ipc.recv.copy_failed</span><span class="sxs-lookup"><span data-stu-id="1a42a-360">ipc.recv.copy_failed</span></span>             | |
| <span data-ttu-id="1a42a-361">ipc.kauth.vnode.mask</span><span class="sxs-lookup"><span data-stu-id="1a42a-361">ipc.kauth.vnode.mask</span></span>             | |
| <span data-ttu-id="1a42a-362">ipc.kauth.vnode.read</span><span class="sxs-lookup"><span data-stu-id="1a42a-362">ipc.kauth.vnode.read</span></span>             | |
| <span data-ttu-id="1a42a-363">ipc.kauth.vnode.write</span><span class="sxs-lookup"><span data-stu-id="1a42a-363">ipc.kauth.vnode.write</span></span>            | |
| <span data-ttu-id="1a42a-364">ipc.kauth.vnode.exec</span><span class="sxs-lookup"><span data-stu-id="1a42a-364">ipc.kauth.vnode.exec</span></span>             | |
| <span data-ttu-id="1a42a-365">ipc.kauth.vnode.del</span><span class="sxs-lookup"><span data-stu-id="1a42a-365">ipc.kauth.vnode.del</span></span>              | |
| <span data-ttu-id="1a42a-366">ipc.kauth.vnode.read_attr</span><span class="sxs-lookup"><span data-stu-id="1a42a-366">ipc.kauth.vnode.read_attr</span></span>        | |
| <span data-ttu-id="1a42a-367">ipc.kauth.vnode.write_attr</span><span class="sxs-lookup"><span data-stu-id="1a42a-367">ipc.kauth.vnode.write_attr</span></span>       | |
| <span data-ttu-id="1a42a-368">ipc.kauth.vnode.read_ex_attr</span><span class="sxs-lookup"><span data-stu-id="1a42a-368">ipc.kauth.vnode.read_ex_attr</span></span>     | |
| <span data-ttu-id="1a42a-369">ipc.kauth.vnode.write_ex_attr</span><span class="sxs-lookup"><span data-stu-id="1a42a-369">ipc.kauth.vnode.write_ex_attr</span></span>    | |
| <span data-ttu-id="1a42a-370">ipc.kauth.vnode.read_sec</span><span class="sxs-lookup"><span data-stu-id="1a42a-370">ipc.kauth.vnode.read_sec</span></span>         | |
| <span data-ttu-id="1a42a-371">ipc.kauth.vnode.write_sec</span><span class="sxs-lookup"><span data-stu-id="1a42a-371">ipc.kauth.vnode.write_sec</span></span>        | |
| <span data-ttu-id="1a42a-372">ipc.kauth.vnode.take_own</span><span class="sxs-lookup"><span data-stu-id="1a42a-372">ipc.kauth.vnode.take_own</span></span>         | |
| <span data-ttu-id="1a42a-373">ipc.kauth.vnode.link</span><span class="sxs-lookup"><span data-stu-id="1a42a-373">ipc.kauth.vnode.link</span></span>             | |
| <span data-ttu-id="1a42a-374">ipc.kauth.vnode.create</span><span class="sxs-lookup"><span data-stu-id="1a42a-374">ipc.kauth.vnode.create</span></span>           | |
| <span data-ttu-id="1a42a-375">ipc.kauth.vnode.move</span><span class="sxs-lookup"><span data-stu-id="1a42a-375">ipc.kauth.vnode.move</span></span>             | |
| <span data-ttu-id="1a42a-376">ipc.kauth.vnode.mount</span><span class="sxs-lookup"><span data-stu-id="1a42a-376">ipc.kauth.vnode.mount</span></span>            | |
| <span data-ttu-id="1a42a-377">ipc.kauth.vnode.denied</span><span class="sxs-lookup"><span data-stu-id="1a42a-377">ipc.kauth.vnode.denied</span></span>           | |
| <span data-ttu-id="1a42a-378">ipc.kauth.vnode.ackd_before_deadline</span><span class="sxs-lookup"><span data-stu-id="1a42a-378">ipc.kauth.vnode.ackd_before_deadline</span></span> | |
| <span data-ttu-id="1a42a-379">ipc.kauth.vnode.missed_deadline</span><span class="sxs-lookup"><span data-stu-id="1a42a-379">ipc.kauth.vnode.missed_deadline</span></span>  | |
| <span data-ttu-id="1a42a-380">ipc.kauth.file_op.mask</span><span class="sxs-lookup"><span data-stu-id="1a42a-380">ipc.kauth.file_op.mask</span></span>           | |
| <span data-ttu-id="1a42a-381">ipc.kauth_file_op.open</span><span class="sxs-lookup"><span data-stu-id="1a42a-381">ipc.kauth_file_op.open</span></span>           | |
| <span data-ttu-id="1a42a-382">ipc.kauth.file_op.close</span><span class="sxs-lookup"><span data-stu-id="1a42a-382">ipc.kauth.file_op.close</span></span>          | |
| <span data-ttu-id="1a42a-383">ipc.kauth.file_op.close_modified</span><span class="sxs-lookup"><span data-stu-id="1a42a-383">ipc.kauth.file_op.close_modified</span></span> | |
| <span data-ttu-id="1a42a-384">ipc.kauth.file_op.move</span><span class="sxs-lookup"><span data-stu-id="1a42a-384">ipc.kauth.file_op.move</span></span>           | |
| <span data-ttu-id="1a42a-385">ipc.kauth.file_op.link</span><span class="sxs-lookup"><span data-stu-id="1a42a-385">ipc.kauth.file_op.link</span></span>           | |
| <span data-ttu-id="1a42a-386">ipc.kauth.file_op.exec</span><span class="sxs-lookup"><span data-stu-id="1a42a-386">ipc.kauth.file_op.exec</span></span>           | |
| <span data-ttu-id="1a42a-387">ipc.kauth.file_op.remove</span><span class="sxs-lookup"><span data-stu-id="1a42a-387">ipc.kauth.file_op.remove</span></span>         | |
| <span data-ttu-id="1a42a-388">ipc.kauth.file_op.unmount</span><span class="sxs-lookup"><span data-stu-id="1a42a-388">ipc.kauth.file_op.unmount</span></span>        | |
| <span data-ttu-id="1a42a-389">ipc.kauth.file_op.fork</span><span class="sxs-lookup"><span data-stu-id="1a42a-389">ipc.kauth.file_op.fork</span></span>           | |
| <span data-ttu-id="1a42a-390">ipc.kauth.file_op.create</span><span class="sxs-lookup"><span data-stu-id="1a42a-390">ipc.kauth.file_op.create</span></span>         | |

## <a name="resources"></a><span data-ttu-id="1a42a-391">リソース</span><span class="sxs-lookup"><span data-stu-id="1a42a-391">Resources</span></span>

- [<span data-ttu-id="1a42a-392">Microsoft におけるプライバシー</span><span class="sxs-lookup"><span data-stu-id="1a42a-392">Privacy at Microsoft</span></span>](https://privacy.microsoft.com/)
