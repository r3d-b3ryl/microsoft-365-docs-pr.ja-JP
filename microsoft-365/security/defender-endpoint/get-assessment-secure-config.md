---
title: デバイスごとのセキュリティで保護された構成評価をエクスポートする
description: DeviceId、 ConfigurationId のすべての一意の組み合わせのエントリを返します。
keywords: api、apis、エクスポート評価、デバイスごとの評価、脆弱性評価レポート、デバイスの脆弱性評価、デバイスの脆弱性レポート、セキュリティで保護された構成評価、セキュリティで保護された構成レポート、ソフトウェアの脆弱性評価、ソフトウェアの脆弱性レポート、コンピューターによる脆弱性レポート、
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 7d39dddf4928b3bcb28fb008bcccd83c67f60177
ms.sourcegitcommit: 4d26a57c37ff7efbb8d235452c78498b06a59714
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/22/2021
ms.locfileid: "53053181"
---
# <a name="export-secure-configuration-assessment-per-device"></a><span data-ttu-id="41443-104">デバイスごとのセキュリティで保護された構成評価をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="41443-104">Export secure configuration assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="41443-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="41443-105">**Applies to:**</span></span>

- [<span data-ttu-id="41443-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="41443-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="41443-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="41443-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="41443-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="41443-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="41443-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="41443-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="41443-110">すべての構成とその状態をデバイス単位で返します。</span><span class="sxs-lookup"><span data-stu-id="41443-110">Returns all of the configurations and their status, on a per-device basis.</span></span>

<span data-ttu-id="41443-111">さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。</span><span class="sxs-lookup"><span data-stu-id="41443-111">There are different API calls to get different types of data.</span></span> <span data-ttu-id="41443-112">データの量が多い場合は、次の 2 つの方法で取得できます。</span><span class="sxs-lookup"><span data-stu-id="41443-112">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="41443-113">[セキュリティで保護された構成評価 **の JSON 応答**](#1-export-secure-configuration-assessment-json-response)をエクスポートする: API は、組織内のすべてのデータを Json 応答として取得します。</span><span class="sxs-lookup"><span data-stu-id="41443-113">[Export secure configuration assessment **JSON response**](#1-export-secure-configuration-assessment-json-response):  The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="41443-114">この方法は _、100 K_ 未満のデバイスを持つ小規模な組織に最適です。</span><span class="sxs-lookup"><span data-stu-id="41443-114">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="41443-115">応答がページ分割されたので、応答から \@ odata.nextLink フィールドを使用して次の結果を取得できます。</span><span class="sxs-lookup"><span data-stu-id="41443-115">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="41443-116">[ファイル経由で安全な構成 **評価を**](#2-export-secure-configuration-assessment-via-files)エクスポートする : この API ソリューションを使用すると、大量のデータを迅速かつ確実に取得できます。</span><span class="sxs-lookup"><span data-stu-id="41443-116">[Export secure configuration assessment **via files**](#2-export-secure-configuration-assessment-via-files): This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="41443-117">そのため、100 K を超えるデバイスを使用する大規模な組織に推奨されます。</span><span class="sxs-lookup"><span data-stu-id="41443-117">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="41443-118">この API は、組織内のすべてのデータをダウンロード ファイルとして取得します。</span><span class="sxs-lookup"><span data-stu-id="41443-118">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="41443-119">応答には、すべてのデータをダウンロードする URL が含Azure Storage。</span><span class="sxs-lookup"><span data-stu-id="41443-119">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="41443-120">この API を使用すると、すべてのデータを次のようにAzure Storageダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="41443-120">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="41443-121">API を呼び出して、すべての組織データを含むダウンロード URL の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="41443-121">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="41443-122">ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="41443-122">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="41443-123">(JSON 応答またはファイルを使用 _して)_ 収集されるデータは、現在の状態の現在のスナップショットであり、歴史的なデータは含まれておりません。</span><span class="sxs-lookup"><span data-stu-id="41443-123">Data that is collected (using either _JSON response_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="41443-124">過去のデータを収集するには、ユーザーがデータを独自のデータ ストレージに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="41443-124">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="41443-125">特に示されていない限り、一覧表示されているエクスポート評価方法はすべて、\*\*\*\* 完全なエクスポートと **_デバイス別_**(デバイス単位とも **_呼_** ばれます) です。</span><span class="sxs-lookup"><span data-stu-id="41443-125">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-secure-configuration-assessment-json-response"></a><span data-ttu-id="41443-126">1. セキュリティで保護された構成評価をエクスポートする (JSON 応答)</span><span class="sxs-lookup"><span data-stu-id="41443-126">1. Export secure configuration assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="41443-127">1.1 API メソッドの説明</span><span class="sxs-lookup"><span data-stu-id="41443-127">1.1 API method description</span></span>

<span data-ttu-id="41443-128">この API 応答には、公開されているデバイスのセキュリティで保護された構成評価が含まれるので、DeviceId、ConfigurationId のすべての一意の組み合わせのエントリが返されます。</span><span class="sxs-lookup"><span data-stu-id="41443-128">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="111-limitations"></a><span data-ttu-id="41443-129">1.1.1 制限事項</span><span class="sxs-lookup"><span data-stu-id="41443-129">1.1.1 Limitations</span></span>

- <span data-ttu-id="41443-130">最大ページ サイズは 200,000 です。</span><span class="sxs-lookup"><span data-stu-id="41443-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="41443-131">この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1000 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="41443-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="41443-132">1.2 アクセス許可</span><span class="sxs-lookup"><span data-stu-id="41443-132">1.2 Permissions</span></span>

<span data-ttu-id="41443-133">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="41443-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="41443-134">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」](apis-intro.md) を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41443-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs](apis-intro.md) for details.</span></span>

<span data-ttu-id="41443-135">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="41443-135">Permission type</span></span> | <span data-ttu-id="41443-136">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="41443-136">Permission</span></span> | <span data-ttu-id="41443-137">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="41443-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="41443-138">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="41443-138">Application</span></span> | <span data-ttu-id="41443-139">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="41443-139">Vulnerability.Read.All</span></span> | <span data-ttu-id="41443-140">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="41443-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="41443-141">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="41443-141">Delegated (work or school account)</span></span> | <span data-ttu-id="41443-142">脆弱性。読み取り</span><span class="sxs-lookup"><span data-stu-id="41443-142">Vulnerability.Read</span></span> | <span data-ttu-id="41443-143">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="41443-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="41443-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="41443-144">1.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="41443-145">1.4 パラメーター</span><span class="sxs-lookup"><span data-stu-id="41443-145">1.4 Parameters</span></span>

- <span data-ttu-id="41443-146">pageSize \( default = 50,000 \) – 応答の結果の数</span><span class="sxs-lookup"><span data-stu-id="41443-146">pageSize \(default = 50,000\) – number of results in response</span></span>

- <span data-ttu-id="41443-147">\$top – 返す結果の数は \( odata.nextLink を返すので、すべてのデータ \@ をプルしない\)</span><span class="sxs-lookup"><span data-stu-id="41443-147">\$top – number of results to return \(doesn’t return \@odata.nextLink and therefore doesn’t pull all the data\)</span></span>

### <a name="15-properties"></a><span data-ttu-id="41443-148">1.5 プロパティ</span><span class="sxs-lookup"><span data-stu-id="41443-148">1.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="41443-149">次の表で定義されているプロパティは、プロパティ ID によってアルファベット順に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="41443-149">The properties defined in the following table are listed alphabetically, by property ID.</span></span>  <span data-ttu-id="41443-150">この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="41443-150">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="41443-151">応答で追加の列が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="41443-151">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="41443-152">これらの列は一時的なもので、削除される場合があります。文書化された列のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="41443-152">These columns are temporary and might be removed, please use only the documented columns.</span></span>
>

<span data-ttu-id="41443-153">プロパティ (ID)</span><span class="sxs-lookup"><span data-stu-id="41443-153">Property (ID)</span></span> | <span data-ttu-id="41443-154">データ型</span><span class="sxs-lookup"><span data-stu-id="41443-154">Data type</span></span> | <span data-ttu-id="41443-155">説明</span><span class="sxs-lookup"><span data-stu-id="41443-155">Description</span></span> | <span data-ttu-id="41443-156">返される値の例</span><span class="sxs-lookup"><span data-stu-id="41443-156">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="41443-157">ConfigurationCategory</span><span class="sxs-lookup"><span data-stu-id="41443-157">ConfigurationCategory</span></span> | <span data-ttu-id="41443-158">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-158">string</span></span> | <span data-ttu-id="41443-159">構成が属するカテゴリまたはグループ: アプリケーション、OS、ネットワーク、アカウント、セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="41443-159">Category or grouping to which the configuration belongs: Application, OS, Network, Accounts, Security controls</span></span> | <span data-ttu-id="41443-160">セキュリティ制御</span><span class="sxs-lookup"><span data-stu-id="41443-160">Security controls</span></span>
<span data-ttu-id="41443-161">ConfigurationId</span><span class="sxs-lookup"><span data-stu-id="41443-161">ConfigurationId</span></span> | <span data-ttu-id="41443-162">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-162">string</span></span> | <span data-ttu-id="41443-163">特定の構成の一意の識別子</span><span class="sxs-lookup"><span data-stu-id="41443-163">Unique identifier for a specific configuration</span></span> | <span data-ttu-id="41443-164">scid-10000</span><span class="sxs-lookup"><span data-stu-id="41443-164">scid-10000</span></span>
<span data-ttu-id="41443-165">ConfigurationImpact</span><span class="sxs-lookup"><span data-stu-id="41443-165">ConfigurationImpact</span></span> | <span data-ttu-id="41443-166">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-166">string</span></span> | <span data-ttu-id="41443-167">構成が全体の構成スコアに与える影響の評価 (1-10)</span><span class="sxs-lookup"><span data-stu-id="41443-167">Rated impact of the configuration to the overall configuration score (1-10)</span></span> | <span data-ttu-id="41443-168">9</span><span class="sxs-lookup"><span data-stu-id="41443-168">9</span></span>
<span data-ttu-id="41443-169">ConfigurationName</span><span class="sxs-lookup"><span data-stu-id="41443-169">ConfigurationName</span></span> | <span data-ttu-id="41443-170">string</span><span class="sxs-lookup"><span data-stu-id="41443-170">string</span></span> | <span data-ttu-id="41443-171">構成の表示名</span><span class="sxs-lookup"><span data-stu-id="41443-171">Display name of the configuration</span></span> | <span data-ttu-id="41443-172">デバイスを Microsoft Defender for Endpoint にオンボードする</span><span class="sxs-lookup"><span data-stu-id="41443-172">Onboard devices to Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="41443-173">ConfigurationSubcategory</span><span class="sxs-lookup"><span data-stu-id="41443-173">ConfigurationSubcategory</span></span> | <span data-ttu-id="41443-174">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-174">string</span></span> | <span data-ttu-id="41443-175">構成が属するサブカテゴリまたはサブグループ。</span><span class="sxs-lookup"><span data-stu-id="41443-175">Subcategory or subgrouping to which the configuration belongs.</span></span> <span data-ttu-id="41443-176">多くの場合、これは特定の機能または機能を説明します。</span><span class="sxs-lookup"><span data-stu-id="41443-176">In many cases, this describes specific capabilities or features.</span></span> | <span data-ttu-id="41443-177">オンボード デバイス</span><span class="sxs-lookup"><span data-stu-id="41443-177">Onboard Devices</span></span>
<span data-ttu-id="41443-178">DeviceId</span><span class="sxs-lookup"><span data-stu-id="41443-178">DeviceId</span></span> | <span data-ttu-id="41443-179">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-179">string</span></span> | <span data-ttu-id="41443-180">サービス内のデバイスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="41443-180">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="41443-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="41443-181">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="41443-182">DeviceName</span><span class="sxs-lookup"><span data-stu-id="41443-182">DeviceName</span></span> | <span data-ttu-id="41443-183">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-183">string</span></span> | <span data-ttu-id="41443-184">デバイスの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="41443-184">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="41443-185">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="41443-185">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="41443-186">IsApplicable</span><span class="sxs-lookup"><span data-stu-id="41443-186">IsApplicable</span></span> | <span data-ttu-id="41443-187">bool</span><span class="sxs-lookup"><span data-stu-id="41443-187">bool</span></span> | <span data-ttu-id="41443-188">構成またはポリシーが適用可能かどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="41443-188">Indicates whether the configuration or policy is applicable</span></span> | <span data-ttu-id="41443-189">true</span><span class="sxs-lookup"><span data-stu-id="41443-189">true</span></span>
<span data-ttu-id="41443-190">IsCompliant</span><span class="sxs-lookup"><span data-stu-id="41443-190">IsCompliant</span></span> | <span data-ttu-id="41443-191">bool</span><span class="sxs-lookup"><span data-stu-id="41443-191">bool</span></span> | <span data-ttu-id="41443-192">構成やポリシーが正しく構成されているかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="41443-192">Indicates whether the configuration or policy is properly configured</span></span> | <span data-ttu-id="41443-193">false</span><span class="sxs-lookup"><span data-stu-id="41443-193">false</span></span>
<span data-ttu-id="41443-194">IsExpectedUserImpact</span><span class="sxs-lookup"><span data-stu-id="41443-194">IsExpectedUserImpact</span></span> | <span data-ttu-id="41443-195">bool</span><span class="sxs-lookup"><span data-stu-id="41443-195">bool</span></span> | <span data-ttu-id="41443-196">構成が適用される場合にユーザーに影響を与えるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="41443-196">Indicates whether there will be user impact if the configuration will be applied</span></span> | <span data-ttu-id="41443-197">true</span><span class="sxs-lookup"><span data-stu-id="41443-197">true</span></span>
<span data-ttu-id="41443-198">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="41443-198">OSPlatform</span></span> | <span data-ttu-id="41443-199">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-199">string</span></span> | <span data-ttu-id="41443-200">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="41443-200">Platform of the operating system running on the device.</span></span> <span data-ttu-id="41443-201">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="41443-201">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="41443-202">詳細については、「tvm でサポートされるオペレーティング システムとプラットフォーム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="41443-202">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="41443-203">Windows10</span><span class="sxs-lookup"><span data-stu-id="41443-203">Windows10</span></span>
<span data-ttu-id="41443-204">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="41443-204">RbacGroupName</span></span> | <span data-ttu-id="41443-205">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-205">string</span></span> | <span data-ttu-id="41443-206">役割ベースのアクセス制御 (RBAC) グループ。</span><span class="sxs-lookup"><span data-stu-id="41443-206">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="41443-207">このデバイスが RBAC グループに割り当てられていない場合、値は "割り当てられていない" になります。</span><span class="sxs-lookup"><span data-stu-id="41443-207">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="41443-208">組織に RBAC グループが含まれている場合、値は "None" になります。</span><span class="sxs-lookup"><span data-stu-id="41443-208">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="41443-209">Servers</span><span class="sxs-lookup"><span data-stu-id="41443-209">Servers</span></span>
<span data-ttu-id="41443-210">RecommendationReference</span><span class="sxs-lookup"><span data-stu-id="41443-210">RecommendationReference</span></span> | <span data-ttu-id="41443-211">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-211">string</span></span> | <span data-ttu-id="41443-212">このソフトウェアに関連する推奨事項 ID への参照。</span><span class="sxs-lookup"><span data-stu-id="41443-212">A reference to the recommendation ID related to this software.</span></span> | <span data-ttu-id="41443-213">sca-_-scid-20000</span><span class="sxs-lookup"><span data-stu-id="41443-213">sca-_-scid-20000</span></span>
<span data-ttu-id="41443-214">Timestamp</span><span class="sxs-lookup"><span data-stu-id="41443-214">Timestamp</span></span> | <span data-ttu-id="41443-215">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-215">string</span></span> | <span data-ttu-id="41443-216">デバイスで構成が最後に表示された時刻</span><span class="sxs-lookup"><span data-stu-id="41443-216">Last time the configuration was seen on the device</span></span> | <span data-ttu-id="41443-217">2020-11-03 10:13:34.8476880</span><span class="sxs-lookup"><span data-stu-id="41443-217">2020-11-03 10:13:34.8476880</span></span>

### <a name="16-examples"></a><span data-ttu-id="41443-218">1.6 例</span><span class="sxs-lookup"><span data-stu-id="41443-218">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="41443-219">1.6.1 要求の例</span><span class="sxs-lookup"><span data-stu-id="41443-219">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5 
```

#### <a name="162-response-example"></a><span data-ttu-id="41443-220">1.6.2 応答の例</span><span class="sxs-lookup"><span data-stu-id="41443-220">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol – Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a><span data-ttu-id="41443-221">2. 安全な構成評価をエクスポートする (ファイル経由)</span><span class="sxs-lookup"><span data-stu-id="41443-221">2. Export secure configuration assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="41443-222">2.1 API メソッドの説明</span><span class="sxs-lookup"><span data-stu-id="41443-222">2.1 API method description</span></span>

<span data-ttu-id="41443-223">この API 応答には、公開されているデバイスのセキュリティで保護された構成評価が含まれるので、DeviceId、ConfigurationId のすべての一意の組み合わせのエントリが返されます。</span><span class="sxs-lookup"><span data-stu-id="41443-223">This API response contains the Secure Configuration Assessment on your exposed devices, and returns an entry for every unique combination of DeviceId, ConfigurationId.</span></span>

#### <a name="212-limitations"></a><span data-ttu-id="41443-224">2.1.2 制限事項</span><span class="sxs-lookup"><span data-stu-id="41443-224">2.1.2 Limitations</span></span>

<span data-ttu-id="41443-225">この API のレート制限は、1 分あたり 5 回の呼び出しと 1 時間あたり 20 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="41443-225">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="41443-226">2.2 アクセス許可</span><span class="sxs-lookup"><span data-stu-id="41443-226">2.2 Permissions</span></span>

<span data-ttu-id="41443-227">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="41443-227">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="41443-228">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="41443-228">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="41443-229">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="41443-229">Permission type</span></span> | <span data-ttu-id="41443-230">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="41443-230">Permission</span></span> | <span data-ttu-id="41443-231">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="41443-231">Permission display name</span></span>
---|---|---
<span data-ttu-id="41443-232">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="41443-232">Application</span></span> | <span data-ttu-id="41443-233">Vulnerability.Read.All</span><span class="sxs-lookup"><span data-stu-id="41443-233">Vulnerability.Read.All</span></span> | <span data-ttu-id="41443-234">\'"脅威と脆弱性の管理" の脆弱性情報を読む\'</span><span class="sxs-lookup"><span data-stu-id="41443-234">\'Read "threat and vulnerability management" vulnerability information\'</span></span>
<span data-ttu-id="41443-235">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="41443-235">Delegated (work or school account)</span></span> | <span data-ttu-id="41443-236">脆弱性。読み取り</span><span class="sxs-lookup"><span data-stu-id="41443-236">Vulnerability.Read</span></span> | <span data-ttu-id="41443-237">\'"脅威と脆弱性の管理" の脆弱性情報を読む\'</span><span class="sxs-lookup"><span data-stu-id="41443-237">\'Read "threat and vulnerability management" vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="41443-238">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="41443-238">2.3 URL</span></span>

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a><span data-ttu-id="41443-239">パラメーター</span><span class="sxs-lookup"><span data-stu-id="41443-239">Parameters</span></span>

- <span data-ttu-id="41443-240">sasValidHours – ダウンロード URL が有効になる時間数 (最大 24 時間)。</span><span class="sxs-lookup"><span data-stu-id="41443-240">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours).</span></span>

### <a name="25-properties"></a><span data-ttu-id="41443-241">2.5 プロパティ</span><span class="sxs-lookup"><span data-stu-id="41443-241">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="41443-242">ファイルは、複数行 Json 形式& gzip 圧縮ファイルです。</span><span class="sxs-lookup"><span data-stu-id="41443-242">The files are gzip compressed & in multiline Json format.</span></span>
>
>- <span data-ttu-id="41443-243">ダウンロード URL は 3 時間のみ有効です。それ以外の場合は、パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="41443-243">The download URLs are only valid for 3 hours; otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="41443-244">データの最大ダウンロード速度を得る場合は、データが存在する同じ Azure リージョンからダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="41443-244">For maximum download speed of your data, you can make sure you are downloading from the same Azure region in which your data resides.</span></span>
>
<span data-ttu-id="41443-245">プロパティ (ID)</span><span class="sxs-lookup"><span data-stu-id="41443-245">Property (ID)</span></span> | <span data-ttu-id="41443-246">データ型</span><span class="sxs-lookup"><span data-stu-id="41443-246">Data type</span></span> | <span data-ttu-id="41443-247">説明</span><span class="sxs-lookup"><span data-stu-id="41443-247">Description</span></span> | <span data-ttu-id="41443-248">返される値の例</span><span class="sxs-lookup"><span data-stu-id="41443-248">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="41443-249">ファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="41443-249">Export files</span></span> | <span data-ttu-id="41443-250">配列 \[ 文字列\]</span><span class="sxs-lookup"><span data-stu-id="41443-250">array\[string\]</span></span> | <span data-ttu-id="41443-251">組織の現在のスナップショットを保持するファイルのダウンロード URL の一覧</span><span class="sxs-lookup"><span data-stu-id="41443-251">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="41443-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="41443-252">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="41443-253">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="41443-253">GeneratedTime</span></span> | <span data-ttu-id="41443-254">文字列</span><span class="sxs-lookup"><span data-stu-id="41443-254">string</span></span> | <span data-ttu-id="41443-255">エクスポートが生成された時刻。</span><span class="sxs-lookup"><span data-stu-id="41443-255">The time that the export was generated.</span></span> | <span data-ttu-id="41443-256">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="41443-256">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="41443-257">2.6 例</span><span class="sxs-lookup"><span data-stu-id="41443-257">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="41443-258">2.6.1 要求の例</span><span class="sxs-lookup"><span data-stu-id="41443-258">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a><span data-ttu-id="41443-259">2.6.2 応答例</span><span class="sxs-lookup"><span data-stu-id="41443-259">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="41443-260">関連項目</span><span class="sxs-lookup"><span data-stu-id="41443-260">See also</span></span>

- [<span data-ttu-id="41443-261">デバイスごとの評価方法とプロパティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="41443-261">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="41443-262">デバイスごとのソフトウェア インベントリ評価のエクスポート</span><span class="sxs-lookup"><span data-stu-id="41443-262">Export software inventory assessment per device</span></span>](get-assessment-software-inventory.md)

- [<span data-ttu-id="41443-263">デバイスごとのソフトウェアの脆弱性評価のエクスポート</span><span class="sxs-lookup"><span data-stu-id="41443-263">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="41443-264">その他の関連</span><span class="sxs-lookup"><span data-stu-id="41443-264">Other related</span></span>

- [<span data-ttu-id="41443-265">リスクベースの脅威& 脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="41443-265">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="41443-266">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="41443-266">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
