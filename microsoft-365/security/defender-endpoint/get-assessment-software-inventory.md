---
title: デバイスごとのソフトウェア インベントリ評価のエクスポート
description: DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。
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
ms.openlocfilehash: 639f850119498222684c4b3804b32a29dda3eac4
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022884"
---
# <a name="export-software-inventory-assessment-per-device"></a><span data-ttu-id="feba0-104">デバイスごとのソフトウェア インベントリ評価のエクスポート</span><span class="sxs-lookup"><span data-stu-id="feba0-104">Export software inventory assessment per device</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="feba0-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="feba0-105">**Applies to:**</span></span>

- [<span data-ttu-id="feba0-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="feba0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="feba0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="feba0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="feba0-108">Microsoft Defender ATP を試してみたいですか?</span><span class="sxs-lookup"><span data-stu-id="feba0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="feba0-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="feba0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

>
<span data-ttu-id="feba0-110">さまざまな種類のデータを取得するために、さまざまな API 呼び出しがあります。</span><span class="sxs-lookup"><span data-stu-id="feba0-110">There are different API calls to get different types of data.</span></span> <span data-ttu-id="feba0-111">データの量が多い場合は、次の 2 つの方法で取得できます。</span><span class="sxs-lookup"><span data-stu-id="feba0-111">Because the amount of data can be large, there are two ways it can be retrieved:</span></span>

- <span data-ttu-id="feba0-112">[ソフトウェア インベントリ評価 **JSON 応答のエクスポート**](#1-export-software-inventory-assessment-json-response) API は、組織内のすべてのデータを Json 応答としてプルします。</span><span class="sxs-lookup"><span data-stu-id="feba0-112">[Export software inventory assessment **JSON response**](#1-export-software-inventory-assessment-json-response) The API pulls all data in your organization as Json responses.</span></span> <span data-ttu-id="feba0-113">この方法は _、100 K_ 未満のデバイスを持つ小規模な組織に最適です。</span><span class="sxs-lookup"><span data-stu-id="feba0-113">This method is best for _small organizations with less than 100-K devices_.</span></span> <span data-ttu-id="feba0-114">応答がページ分割されたので、応答から \@ odata.nextLink フィールドを使用して次の結果を取得できます。</span><span class="sxs-lookup"><span data-stu-id="feba0-114">The response is paginated, so you can use the \@odata.nextLink field from the response to fetch the next results.</span></span>

- <span data-ttu-id="feba0-115">[ファイルを介してソフトウェア インベントリ評価 **をエクスポートする**](#2-export-software-inventory-assessment-via-files)  この API ソリューションを使用すると、大量のデータを高速かつ確実に取得できます。</span><span class="sxs-lookup"><span data-stu-id="feba0-115">[Export software inventory assessment **via files**](#2-export-software-inventory-assessment-via-files)  This API solution enables pulling larger amounts of data faster and more reliably.</span></span> <span data-ttu-id="feba0-116">そのため、100 K を超えるデバイスを使用する大規模な組織に推奨されます。</span><span class="sxs-lookup"><span data-stu-id="feba0-116">Therefore, it is recommended for large organizations, with more than 100-K devices.</span></span> <span data-ttu-id="feba0-117">この API は、組織内のすべてのデータをダウンロード ファイルとして取得します。</span><span class="sxs-lookup"><span data-stu-id="feba0-117">This API pulls all data in your organization as download files.</span></span> <span data-ttu-id="feba0-118">応答には、すべてのデータをダウンロードする URL が含Azure Storage。</span><span class="sxs-lookup"><span data-stu-id="feba0-118">The response contains URLs to download all the data from Azure Storage.</span></span> <span data-ttu-id="feba0-119">この API を使用すると、すべてのデータを次のようにAzure Storageダウンロードできます。</span><span class="sxs-lookup"><span data-stu-id="feba0-119">This API enables you to download all your data from Azure Storage as follows:</span></span>

  - <span data-ttu-id="feba0-120">API を呼び出して、すべての組織データを含むダウンロード URL の一覧を取得します。</span><span class="sxs-lookup"><span data-stu-id="feba0-120">Call the API to get a list of download URLs with all your organization data.</span></span>

  - <span data-ttu-id="feba0-121">ダウンロード URL を使用してすべてのファイルをダウンロードし、必要に合ったデータを処理します。</span><span class="sxs-lookup"><span data-stu-id="feba0-121">Download all the files using the download URLs and process the data as you like.</span></span>

<span data-ttu-id="feba0-122">収集されるデータ _(OData_ またはファイル _経由)_ は、現在の状態の現在のスナップショットであり、古いデータは含まれておりません。</span><span class="sxs-lookup"><span data-stu-id="feba0-122">Data that is collected (using either _OData_ or _via files_) is the current snapshot of the current state, and does not contain historic data.</span></span> <span data-ttu-id="feba0-123">過去のデータを収集するには、ユーザーがデータを独自のデータ ストレージに保存する必要があります。</span><span class="sxs-lookup"><span data-stu-id="feba0-123">In order to collect historic data, customers must save the data in their own data storages.</span></span>

> [!Note]
>
> <span data-ttu-id="feba0-124">特に示されていない限り、一覧表示されているエクスポート評価方法はすべて、\*\*\*\* 完全なエクスポートと **_デバイス別_**(デバイス単位とも **_呼_** ばれます) です。</span><span class="sxs-lookup"><span data-stu-id="feba0-124">Unless indicated otherwise, all export assessment methods listed are **_full export_** and **_by device_** (also referred to as **_per device_**).</span></span>

## <a name="1-export-software-inventory-assessment-json-response"></a><span data-ttu-id="feba0-125">1. ソフトウェア インベントリ評価のエクスポート (JSON 応答)</span><span class="sxs-lookup"><span data-stu-id="feba0-125">1. Export software inventory assessment (JSON response)</span></span>

### <a name="11-api-method-description"></a><span data-ttu-id="feba0-126">1.1 API メソッドの説明</span><span class="sxs-lookup"><span data-stu-id="feba0-126">1.1 API method description</span></span>

<span data-ttu-id="feba0-127">この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="feba0-127">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="feba0-128">DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="feba0-128">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="limitations"></a><span data-ttu-id="feba0-129">制限事項</span><span class="sxs-lookup"><span data-stu-id="feba0-129">Limitations</span></span>

- <span data-ttu-id="feba0-130">最大ページ サイズは 200,000 です。</span><span class="sxs-lookup"><span data-stu-id="feba0-130">Maximum page size is 200,000.</span></span>

- <span data-ttu-id="feba0-131">この API のレート制限は、1 分あたり 30 回の呼び出しと 1 時間あたり 1000 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="feba0-131">Rate limitations for this API are 30 calls per minute and 1000 calls per hour.</span></span>

### <a name="12-permissions"></a><span data-ttu-id="feba0-132">1.2 アクセス許可</span><span class="sxs-lookup"><span data-stu-id="feba0-132">1.2 Permissions</span></span>

<span data-ttu-id="feba0-133">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="feba0-133">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="feba0-134">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="feba0-134">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="feba0-135">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="feba0-135">Permission type</span></span> | <span data-ttu-id="feba0-136">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="feba0-136">Permission</span></span> | <span data-ttu-id="feba0-137">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="feba0-137">Permission display name</span></span>
---|---|---
<span data-ttu-id="feba0-138">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="feba0-138">Application</span></span> | <span data-ttu-id="feba0-139">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="feba0-139">Software.Read.All</span></span> | <span data-ttu-id="feba0-140">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="feba0-140">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="feba0-141">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="feba0-141">Delegated (work or school account)</span></span> | <span data-ttu-id="feba0-142">Software.Read</span><span class="sxs-lookup"><span data-stu-id="feba0-142">Software.Read</span></span> | <span data-ttu-id="feba0-143">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="feba0-143">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="13-url"></a><span data-ttu-id="feba0-144">1.3 URL</span><span class="sxs-lookup"><span data-stu-id="feba0-144">1.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a><span data-ttu-id="feba0-145">1.4 パラメーター</span><span class="sxs-lookup"><span data-stu-id="feba0-145">1.4 Parameters</span></span>

- <span data-ttu-id="feba0-146">pageSize (既定値 = 50,000) – 応答の結果の数。</span><span class="sxs-lookup"><span data-stu-id="feba0-146">pageSize (default = 50,000) – number of results in response.</span></span>

- <span data-ttu-id="feba0-147">$top – 返す結果の数 (@odata.nextLink を返すので、すべてのデータを取得しない)</span><span class="sxs-lookup"><span data-stu-id="feba0-147">$top – number of results to return (doesn’t return @odata.nextLink and therefore doesn’t pull all the data)</span></span>

### <a name="15-properties"></a><span data-ttu-id="feba0-148">1.5 プロパティ</span><span class="sxs-lookup"><span data-stu-id="feba0-148">1.5 Properties</span></span>

>[!NOTE]
>
>- <span data-ttu-id="feba0-149">各レコードのデータは約 0.5 KB です。</span><span class="sxs-lookup"><span data-stu-id="feba0-149">Each record is approximately 0.5KB of data.</span></span> <span data-ttu-id="feba0-150">正しい pageSize パラメーターを選択する場合は、これを考慮する必要があります。</span><span class="sxs-lookup"><span data-stu-id="feba0-150">You should take this into account when choosing the correct pageSize parameter for you.</span></span>
>
>- <span data-ttu-id="feba0-151">次の表で定義されているプロパティは、プロパティ ID によってアルファベット順に一覧表示されます。</span><span class="sxs-lookup"><span data-stu-id="feba0-151">The properties defined in the following table are listed alphabetically, by property ID.</span></span> <span data-ttu-id="feba0-152">この API を実行する場合、結果の出力は必ずしもこの表に示されているのと同じ順序で返されるとは限りません。</span><span class="sxs-lookup"><span data-stu-id="feba0-152">When running this API, the resulting output will not necessarily be returned in the same order listed in this table.</span></span>
>
>- <span data-ttu-id="feba0-153">応答で追加の列が返される場合があります。</span><span class="sxs-lookup"><span data-stu-id="feba0-153">Some additional columns might be returned in the response.</span></span> <span data-ttu-id="feba0-154">これらの列は一時的なもので、削除される場合があります。文書化された列のみを使用してください。</span><span class="sxs-lookup"><span data-stu-id="feba0-154">These columns are temporary and might be removed, please use only the documented columns.</span></span>

<br/>

<span data-ttu-id="feba0-155">プロパティ (ID)</span><span class="sxs-lookup"><span data-stu-id="feba0-155">Property (ID)</span></span> | <span data-ttu-id="feba0-156">データ型</span><span class="sxs-lookup"><span data-stu-id="feba0-156">Data type</span></span> | <span data-ttu-id="feba0-157">説明</span><span class="sxs-lookup"><span data-stu-id="feba0-157">Description</span></span> | <span data-ttu-id="feba0-158">返される値の例</span><span class="sxs-lookup"><span data-stu-id="feba0-158">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="feba0-159">DeviceId</span><span class="sxs-lookup"><span data-stu-id="feba0-159">DeviceId</span></span> | <span data-ttu-id="feba0-160">string</span><span class="sxs-lookup"><span data-stu-id="feba0-160">string</span></span> | <span data-ttu-id="feba0-161">サービス内のデバイスの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="feba0-161">Unique identifier for the device in the service.</span></span> | <span data-ttu-id="feba0-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span><span class="sxs-lookup"><span data-stu-id="feba0-162">9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1</span></span>
<span data-ttu-id="feba0-163">DeviceName</span><span class="sxs-lookup"><span data-stu-id="feba0-163">DeviceName</span></span> | <span data-ttu-id="feba0-164">string</span><span class="sxs-lookup"><span data-stu-id="feba0-164">string</span></span> | <span data-ttu-id="feba0-165">デバイスの完全修飾ドメイン名 (FQDN)。</span><span class="sxs-lookup"><span data-stu-id="feba0-165">Fully qualified domain name (FQDN) of the device.</span></span> | <span data-ttu-id="feba0-166">johnlaptop.europe.contoso.com</span><span class="sxs-lookup"><span data-stu-id="feba0-166">johnlaptop.europe.contoso.com</span></span>
<span data-ttu-id="feba0-167">DiskPaths</span><span class="sxs-lookup"><span data-stu-id="feba0-167">DiskPaths</span></span> | <span data-ttu-id="feba0-168">Array[string]</span><span class="sxs-lookup"><span data-stu-id="feba0-168">Array[string]</span></span>  | <span data-ttu-id="feba0-169">製品がデバイスにインストールされていることを示すディスク証拠。</span><span class="sxs-lookup"><span data-stu-id="feba0-169">Disk evidence that the product is installed on the device.</span></span> | <span data-ttu-id="feba0-170">[ "C: \\プログラム ファイル (x86) \\ Microsoft \\ Silverlight \\ アプリケーション \\silverlight.exe" ]</span><span class="sxs-lookup"><span data-stu-id="feba0-170">[ "C:\\Program Files (x86)\\Microsoft\\Silverlight\\Application\\silverlight.exe" ]</span></span>
<span data-ttu-id="feba0-171">EndOfSupportDate</span><span class="sxs-lookup"><span data-stu-id="feba0-171">EndOfSupportDate</span></span> | <span data-ttu-id="feba0-172">string</span><span class="sxs-lookup"><span data-stu-id="feba0-172">string</span></span> | <span data-ttu-id="feba0-173">このソフトウェアのサポートが終了または終了する日付。</span><span class="sxs-lookup"><span data-stu-id="feba0-173">The date in which support for this software has or will end.</span></span> | <span data-ttu-id="feba0-174">2020-12-30</span><span class="sxs-lookup"><span data-stu-id="feba0-174">2020-12-30</span></span>
<span data-ttu-id="feba0-175">EndOfSupportStatus</span><span class="sxs-lookup"><span data-stu-id="feba0-175">EndOfSupportStatus</span></span> | <span data-ttu-id="feba0-176">string</span><span class="sxs-lookup"><span data-stu-id="feba0-176">string</span></span> | <span data-ttu-id="feba0-177">サポートの状態の終了。</span><span class="sxs-lookup"><span data-stu-id="feba0-177">End of support status.</span></span> <span data-ttu-id="feba0-178">これらの可能な値を含めることができます。 なし、EOS バージョン、今後の EOS バージョン、EOS ソフトウェア、今後の EOS ソフトウェア。</span><span class="sxs-lookup"><span data-stu-id="feba0-178">Can contain these possible values: None, EOS Version, Upcoming EOS Version, EOS Software, Upcoming EOS Software.</span></span> | <span data-ttu-id="feba0-179">今後の EOS</span><span class="sxs-lookup"><span data-stu-id="feba0-179">Upcoming EOS</span></span>
<span data-ttu-id="feba0-180">ID</span><span class="sxs-lookup"><span data-stu-id="feba0-180">Id</span></span> | <span data-ttu-id="feba0-181">string</span><span class="sxs-lookup"><span data-stu-id="feba0-181">string</span></span> | <span data-ttu-id="feba0-182">レコードの一意の識別子。</span><span class="sxs-lookup"><span data-stu-id="feba0-182">Unique identifier for the record.</span></span> | <span data-ttu-id="feba0-183">123ABG55_573AG&mnp!</span><span class="sxs-lookup"><span data-stu-id="feba0-183">123ABG55_573AG&mnp!</span></span>
<span data-ttu-id="feba0-184">NumberOfWeaknesses</span><span class="sxs-lookup"><span data-stu-id="feba0-184">NumberOfWeaknesses</span></span> | <span data-ttu-id="feba0-185">int</span><span class="sxs-lookup"><span data-stu-id="feba0-185">int</span></span> | <span data-ttu-id="feba0-186">このデバイス上のこのソフトウェアの弱点の数</span><span class="sxs-lookup"><span data-stu-id="feba0-186">Number of weaknesses on this software on this device</span></span> | <span data-ttu-id="feba0-187">3</span><span class="sxs-lookup"><span data-stu-id="feba0-187">3</span></span>
<span data-ttu-id="feba0-188">OSPlatform</span><span class="sxs-lookup"><span data-stu-id="feba0-188">OSPlatform</span></span> | <span data-ttu-id="feba0-189">string</span><span class="sxs-lookup"><span data-stu-id="feba0-189">string</span></span> | <span data-ttu-id="feba0-190">デバイスで実行されているオペレーティング システムのプラットフォーム。</span><span class="sxs-lookup"><span data-stu-id="feba0-190">Platform of the operating system running on the device.</span></span> <span data-ttu-id="feba0-191">これは、Windows 10 や Windows 7 などの同じファミリ内のバリエーションを含む、特定のオペレーティング システムを示します。</span><span class="sxs-lookup"><span data-stu-id="feba0-191">This indicates specific operating systems, including variations within the same family, such as Windows 10 and Windows 7.</span></span> <span data-ttu-id="feba0-192">詳細については、「tvm でサポートされるオペレーティング システムとプラットフォーム」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="feba0-192">See tvm supported operating systems and platforms for details.</span></span> | <span data-ttu-id="feba0-193">Windows10</span><span class="sxs-lookup"><span data-stu-id="feba0-193">Windows10</span></span>
<span data-ttu-id="feba0-194">RbacGroupName</span><span class="sxs-lookup"><span data-stu-id="feba0-194">RbacGroupName</span></span> | <span data-ttu-id="feba0-195">string</span><span class="sxs-lookup"><span data-stu-id="feba0-195">string</span></span> | <span data-ttu-id="feba0-196">役割ベースのアクセス制御 (RBAC) グループ。</span><span class="sxs-lookup"><span data-stu-id="feba0-196">The role-based access control (RBAC) group.</span></span> <span data-ttu-id="feba0-197">このデバイスが RBAC グループに割り当てられていない場合、値は "割り当てられていない" になります。</span><span class="sxs-lookup"><span data-stu-id="feba0-197">If this device is not assigned to any RBAC group, the value will be “Unassigned.”</span></span> <span data-ttu-id="feba0-198">組織に RBAC グループが含まれている場合、値は "None" になります。</span><span class="sxs-lookup"><span data-stu-id="feba0-198">If the organization doesn’t contain any RBAC groups, the value will be “None.”</span></span> | <span data-ttu-id="feba0-199">Servers</span><span class="sxs-lookup"><span data-stu-id="feba0-199">Servers</span></span>
<span data-ttu-id="feba0-200">RegistryPaths</span><span class="sxs-lookup"><span data-stu-id="feba0-200">RegistryPaths</span></span> | <span data-ttu-id="feba0-201">Array[string]</span><span class="sxs-lookup"><span data-stu-id="feba0-201">Array[string]</span></span> | <span data-ttu-id="feba0-202">製品がデバイスにインストールされていることを示すレジストリ証拠。</span><span class="sxs-lookup"><span data-stu-id="feba0-202">Registry evidence that the product is installed in the device.</span></span> | <span data-ttu-id="feba0-203">[ "HKEY_LOCAL_MACHINE \\SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion Uninstall Microsoft \\ \\ Silverlight" ]</span><span class="sxs-lookup"><span data-stu-id="feba0-203">[ "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Silverlight" ]</span></span>
<span data-ttu-id="feba0-204">SoftwareFirstSeenTimestamp</span><span class="sxs-lookup"><span data-stu-id="feba0-204">SoftwareFirstSeenTimestamp</span></span> | <span data-ttu-id="feba0-205">string</span><span class="sxs-lookup"><span data-stu-id="feba0-205">string</span></span> | <span data-ttu-id="feba0-206">このソフトウェアがデバイスで初めて見られた。</span><span class="sxs-lookup"><span data-stu-id="feba0-206">The first time this software was seen on the device.</span></span> | <span data-ttu-id="feba0-207">2019-04-07 02:06:47</span><span class="sxs-lookup"><span data-stu-id="feba0-207">2019-04-07 02:06:47</span></span>
<span data-ttu-id="feba0-208">SoftwareName</span><span class="sxs-lookup"><span data-stu-id="feba0-208">SoftwareName</span></span> | <span data-ttu-id="feba0-209">string</span><span class="sxs-lookup"><span data-stu-id="feba0-209">string</span></span> | <span data-ttu-id="feba0-210">ソフトウェア製品の名前。</span><span class="sxs-lookup"><span data-stu-id="feba0-210">Name of the software product.</span></span> | <span data-ttu-id="feba0-211">Silverlight</span><span class="sxs-lookup"><span data-stu-id="feba0-211">Silverlight</span></span>
<span data-ttu-id="feba0-212">SoftwareVendor</span><span class="sxs-lookup"><span data-stu-id="feba0-212">SoftwareVendor</span></span> | <span data-ttu-id="feba0-213">string</span><span class="sxs-lookup"><span data-stu-id="feba0-213">string</span></span> | <span data-ttu-id="feba0-214">ソフトウェア ベンダーの名前。</span><span class="sxs-lookup"><span data-stu-id="feba0-214">Name of the software vendor.</span></span> | <span data-ttu-id="feba0-215">microsoft</span><span class="sxs-lookup"><span data-stu-id="feba0-215">microsoft</span></span>
<span data-ttu-id="feba0-216">SoftwareVersion</span><span class="sxs-lookup"><span data-stu-id="feba0-216">SoftwareVersion</span></span> | <span data-ttu-id="feba0-217">string</span><span class="sxs-lookup"><span data-stu-id="feba0-217">string</span></span> | <span data-ttu-id="feba0-218">ソフトウェア製品のバージョン番号。</span><span class="sxs-lookup"><span data-stu-id="feba0-218">Version number of the software product.</span></span> | <span data-ttu-id="feba0-219">81.0.4044.138</span><span class="sxs-lookup"><span data-stu-id="feba0-219">81.0.4044.138</span></span>

### <a name="16-examples"></a><span data-ttu-id="feba0-220">1.6 例</span><span class="sxs-lookup"><span data-stu-id="feba0-220">1.6 Examples</span></span>

#### <a name="161-request-example"></a><span data-ttu-id="feba0-221">1.6.1 要求の例</span><span class="sxs-lookup"><span data-stu-id="feba0-221">1.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z 
```

#### <a name="162-response-example"></a><span data-ttu-id="feba0-222">1.6.2 応答の例</span><span class="sxs-lookup"><span data-stu-id="feba0-222">1.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a><span data-ttu-id="feba0-223">2. ソフトウェア インベントリ評価のエクスポート (ファイル経由)</span><span class="sxs-lookup"><span data-stu-id="feba0-223">2. Export software inventory assessment (via files)</span></span>

### <a name="21-api-method-description"></a><span data-ttu-id="feba0-224">2.1 API メソッドの説明</span><span class="sxs-lookup"><span data-stu-id="feba0-224">2.1 API method description</span></span>

<span data-ttu-id="feba0-225">この API 応答には、デバイスごとにインストールされているソフトウェアのすべてのデータが含まれる。</span><span class="sxs-lookup"><span data-stu-id="feba0-225">This API response contains all the data of installed software per device.</span></span> <span data-ttu-id="feba0-226">DeviceId、SoftwareVendor、SoftwareName、SoftwareVersion のすべての一意の組み合わせのエントリを含むテーブルを返します。</span><span class="sxs-lookup"><span data-stu-id="feba0-226">Returns a table with an entry for every unique combination of DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion.</span></span>

#### <a name="211-limitations"></a><span data-ttu-id="feba0-227">2.1.1 制限事項</span><span class="sxs-lookup"><span data-stu-id="feba0-227">2.1.1 Limitations</span></span>

<span data-ttu-id="feba0-228">この API のレート制限は、1 分あたり 5 回の呼び出しと 1 時間あたり 20 回の呼び出しです。</span><span class="sxs-lookup"><span data-stu-id="feba0-228">Rate limitations for this API are 5 calls per minute and 20 calls per hour.</span></span>

### <a name="22-permissions"></a><span data-ttu-id="feba0-229">2.2 アクセス許可</span><span class="sxs-lookup"><span data-stu-id="feba0-229">2.2 Permissions</span></span>

<span data-ttu-id="feba0-230">この API を呼び出すには、次のいずれかのアクセス許可が必要です。</span><span class="sxs-lookup"><span data-stu-id="feba0-230">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="feba0-231">アクセス許可の選択方法など、詳細については [、「Use Microsoft Defender for Endpoint API」を参照してください。](apis-intro.md)</span><span class="sxs-lookup"><span data-stu-id="feba0-231">To learn more, including how to choose permissions, see [Use Microsoft Defender for Endpoint APIs for details.](apis-intro.md)</span></span>

<span data-ttu-id="feba0-232">アクセス許可の種類</span><span class="sxs-lookup"><span data-stu-id="feba0-232">Permission type</span></span> | <span data-ttu-id="feba0-233">アクセス許可</span><span class="sxs-lookup"><span data-stu-id="feba0-233">Permission</span></span> | <span data-ttu-id="feba0-234">アクセス許可の表示名</span><span class="sxs-lookup"><span data-stu-id="feba0-234">Permission display name</span></span>
---|---|---
<span data-ttu-id="feba0-235">アプリケーション</span><span class="sxs-lookup"><span data-stu-id="feba0-235">Application</span></span> | <span data-ttu-id="feba0-236">Software.Read.All</span><span class="sxs-lookup"><span data-stu-id="feba0-236">Software.Read.All</span></span> | <span data-ttu-id="feba0-237">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="feba0-237">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>
<span data-ttu-id="feba0-238">委任 (職場または学校のアカウント)</span><span class="sxs-lookup"><span data-stu-id="feba0-238">Delegated (work or school account)</span></span> | <span data-ttu-id="feba0-239">Software.Read</span><span class="sxs-lookup"><span data-stu-id="feba0-239">Software.Read</span></span> | <span data-ttu-id="feba0-240">\'脅威と脆弱性管理の脆弱性情報の読み取り\'</span><span class="sxs-lookup"><span data-stu-id="feba0-240">\'Read Threat and Vulnerability Management vulnerability information\'</span></span>

### <a name="23-url"></a><span data-ttu-id="feba0-241">2.3 URL</span><span class="sxs-lookup"><span data-stu-id="feba0-241">2.3 URL</span></span>

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a><span data-ttu-id="feba0-242">パラメーター</span><span class="sxs-lookup"><span data-stu-id="feba0-242">Parameters</span></span>

- <span data-ttu-id="feba0-243">sasValidHours – ダウンロード URL が有効になる時間数 (最大 24 時間)</span><span class="sxs-lookup"><span data-stu-id="feba0-243">sasValidHours – The number of hours that the download URLs will be valid for (Maximum 24 hours)</span></span>

### <a name="25-properties"></a><span data-ttu-id="feba0-244">2.5 プロパティ</span><span class="sxs-lookup"><span data-stu-id="feba0-244">2.5 Properties</span></span>

>[!Note]
>
>- <span data-ttu-id="feba0-245">ファイルは、複数行 JSON 形式& gzip 圧縮ファイルです。</span><span class="sxs-lookup"><span data-stu-id="feba0-245">The files are gzip compressed & in multiline JSON format.</span></span>
>
>- <span data-ttu-id="feba0-246">ダウンロード URL は 3 時間のみ有効です。</span><span class="sxs-lookup"><span data-stu-id="feba0-246">The download URLs are only valid for 3 hours.</span></span> <span data-ttu-id="feba0-247">それ以外の場合は、パラメーターを使用できます。</span><span class="sxs-lookup"><span data-stu-id="feba0-247">Otherwise you can use the parameter.</span></span>
>
>- <span data-ttu-id="feba0-248">データの最大ダウンロード速度を得る場合は、データが存在するのと同じ Azure 地域からダウンロードしてください。</span><span class="sxs-lookup"><span data-stu-id="feba0-248">For maximum download speed of your data, you can make sure you are downloading from the same Azure region that your data resides.</span></span>

<br/><br/>

<span data-ttu-id="feba0-249">プロパティ (ID)</span><span class="sxs-lookup"><span data-stu-id="feba0-249">Property (ID)</span></span> | <span data-ttu-id="feba0-250">データ型</span><span class="sxs-lookup"><span data-stu-id="feba0-250">Data type</span></span> | <span data-ttu-id="feba0-251">説明</span><span class="sxs-lookup"><span data-stu-id="feba0-251">Description</span></span> | <span data-ttu-id="feba0-252">返される値の例</span><span class="sxs-lookup"><span data-stu-id="feba0-252">Example of a returned value</span></span>
:---|:---|:---|:---
<span data-ttu-id="feba0-253">ファイルのエクスポート</span><span class="sxs-lookup"><span data-stu-id="feba0-253">Export files</span></span> | <span data-ttu-id="feba0-254">配列 \[ 文字列\]</span><span class="sxs-lookup"><span data-stu-id="feba0-254">array\[string\]</span></span> | <span data-ttu-id="feba0-255">組織の現在のスナップショットを保持するファイルのダウンロード URL の一覧</span><span class="sxs-lookup"><span data-stu-id="feba0-255">A list of download URLs for files holding the current snapshot of the organization</span></span> | <span data-ttu-id="feba0-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span><span class="sxs-lookup"><span data-stu-id="feba0-256">[  Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1”, “https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2” ]</span></span>
<span data-ttu-id="feba0-257">GeneratedTime</span><span class="sxs-lookup"><span data-stu-id="feba0-257">GeneratedTime</span></span> | <span data-ttu-id="feba0-258">string</span><span class="sxs-lookup"><span data-stu-id="feba0-258">string</span></span> | <span data-ttu-id="feba0-259">エクスポートが生成された時刻。</span><span class="sxs-lookup"><span data-stu-id="feba0-259">The time that the export was generated.</span></span> | <span data-ttu-id="feba0-260">2021-05-20T08:00:00Z ]</span><span class="sxs-lookup"><span data-stu-id="feba0-260">2021-05-20T08:00:00Z  ]</span></span>

### <a name="26-examples"></a><span data-ttu-id="feba0-261">2.6 例</span><span class="sxs-lookup"><span data-stu-id="feba0-261">2.6 Examples</span></span>

#### <a name="261-request-example"></a><span data-ttu-id="feba0-262">2.6.1 要求の例</span><span class="sxs-lookup"><span data-stu-id="feba0-262">2.6.1 Request example</span></span>

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a><span data-ttu-id="feba0-263">2.6.2 応答例</span><span class="sxs-lookup"><span data-stu-id="feba0-263">2.6.2 Response example</span></span>

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a><span data-ttu-id="feba0-264">関連項目</span><span class="sxs-lookup"><span data-stu-id="feba0-264">See also</span></span>

- [<span data-ttu-id="feba0-265">デバイスごとの評価方法とプロパティのエクスポート</span><span class="sxs-lookup"><span data-stu-id="feba0-265">Export assessment methods and properties per device</span></span>](get-assessment-methods-properties.md)

- [<span data-ttu-id="feba0-266">デバイスごとのセキュリティで保護された構成評価をエクスポートする</span><span class="sxs-lookup"><span data-stu-id="feba0-266">Export secure configuration assessment per device</span></span>](get-assessment-secure-config.md)

- [<span data-ttu-id="feba0-267">デバイスごとのソフトウェアの脆弱性評価のエクスポート</span><span class="sxs-lookup"><span data-stu-id="feba0-267">Export software vulnerabilities assessment per device</span></span>](get-assessment-software-vulnerabilities.md)

<span data-ttu-id="feba0-268">その他の関連</span><span class="sxs-lookup"><span data-stu-id="feba0-268">Other related</span></span>

- [<span data-ttu-id="feba0-269">リスクベースの脅威& 脆弱性の管理</span><span class="sxs-lookup"><span data-stu-id="feba0-269">Risk-based threat & vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)

- [<span data-ttu-id="feba0-270">組織の脆弱性</span><span class="sxs-lookup"><span data-stu-id="feba0-270">Vulnerabilities in your organization</span></span>](tvm-weaknesses.md)
