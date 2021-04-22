---
title: 高度なハンティング スキーマの DeviceFileCertificateInfo テーブル
description: 高度なハンティング スキーマの DeviceFileCertificateInfo テーブルのファイル署名情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、Microsoft 365 Defender、microsoft 365、m365、検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、データ型、デジタル署名、証明書、ファイル署名、DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 272896c745386f13fc0e36301c5c16f5f24dbb42
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933675"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="ea4bd-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="ea4bd-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ea4bd-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="ea4bd-105">**Applies to:**</span></span>
- <span data-ttu-id="ea4bd-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ea4bd-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ea4bd-107">高度 `DeviceFileCertificateInfo` な検索スキーマ [の表](advanced-hunting-overview.md) には、ファイル署名証明書に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="ea4bd-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="ea4bd-108">次の表は、エンドポイント上のファイルで定期的に実行される証明書検証アクティビティから取得したデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="ea4bd-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="ea4bd-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ea4bd-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ea4bd-110">列名</span><span class="sxs-lookup"><span data-stu-id="ea4bd-110">Column name</span></span> | <span data-ttu-id="ea4bd-111">データ型</span><span class="sxs-lookup"><span data-stu-id="ea4bd-111">Data type</span></span> | <span data-ttu-id="ea4bd-112">説明</span><span class="sxs-lookup"><span data-stu-id="ea4bd-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ea4bd-113">日付型</span><span class="sxs-lookup"><span data-stu-id="ea4bd-113">datetime</span></span> | <span data-ttu-id="ea4bd-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="ea4bd-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="ea4bd-115">string</span><span class="sxs-lookup"><span data-stu-id="ea4bd-115">string</span></span> | <span data-ttu-id="ea4bd-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="ea4bd-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="ea4bd-117">string</span><span class="sxs-lookup"><span data-stu-id="ea4bd-117">string</span></span> | <span data-ttu-id="ea4bd-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="ea4bd-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="ea4bd-119">文字列</span><span class="sxs-lookup"><span data-stu-id="ea4bd-119">string</span></span> | <span data-ttu-id="ea4bd-120">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="ea4bd-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="ea4bd-121">ブール値</span><span class="sxs-lookup"><span data-stu-id="ea4bd-121">boolean</span></span> | <span data-ttu-id="ea4bd-122">ファイルが署名されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea4bd-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="ea4bd-123">string</span><span class="sxs-lookup"><span data-stu-id="ea4bd-123">string</span></span> | <span data-ttu-id="ea4bd-124">署名情報をファイル自体に埋め込みコンテンツとして読み取ったか、外部カタログ ファイルから読み取ったかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea4bd-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="ea4bd-125">string</span><span class="sxs-lookup"><span data-stu-id="ea4bd-125">string</span></span> | <span data-ttu-id="ea4bd-126">ファイルの署名者に関する情報</span><span class="sxs-lookup"><span data-stu-id="ea4bd-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="ea4bd-127">string</span><span class="sxs-lookup"><span data-stu-id="ea4bd-127">string</span></span> | <span data-ttu-id="ea4bd-128">署名者を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="ea4bd-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="ea4bd-129">string</span><span class="sxs-lookup"><span data-stu-id="ea4bd-129">string</span></span> | <span data-ttu-id="ea4bd-130">発行元証明機関 (CA) に関する情報</span><span class="sxs-lookup"><span data-stu-id="ea4bd-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="ea4bd-131">string</span><span class="sxs-lookup"><span data-stu-id="ea4bd-131">string</span></span> | <span data-ttu-id="ea4bd-132">発行元証明機関 (CA) を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="ea4bd-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="ea4bd-133">string</span><span class="sxs-lookup"><span data-stu-id="ea4bd-133">string</span></span> | <span data-ttu-id="ea4bd-134">発行元証明機関 (CA) に固有の証明書の識別子</span><span class="sxs-lookup"><span data-stu-id="ea4bd-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="ea4bd-135">string</span><span class="sxs-lookup"><span data-stu-id="ea4bd-135">string</span></span> |  <span data-ttu-id="ea4bd-136">証明書と証明書失効リスト (CRL) を含むネットワーク共有の URL を示す JSON 配列</span><span class="sxs-lookup"><span data-stu-id="ea4bd-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="ea4bd-137">日付型</span><span class="sxs-lookup"><span data-stu-id="ea4bd-137">datetime</span></span> | <span data-ttu-id="ea4bd-138">証明書が作成された日時</span><span class="sxs-lookup"><span data-stu-id="ea4bd-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="ea4bd-139">日付型</span><span class="sxs-lookup"><span data-stu-id="ea4bd-139">datetime</span></span> | <span data-ttu-id="ea4bd-140">証明書の有効期限が設定されている日時</span><span class="sxs-lookup"><span data-stu-id="ea4bd-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="ea4bd-141">日付型</span><span class="sxs-lookup"><span data-stu-id="ea4bd-141">datetime</span></span> | <span data-ttu-id="ea4bd-142">証明書が署名された日時</span><span class="sxs-lookup"><span data-stu-id="ea4bd-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="ea4bd-143">ブール値</span><span class="sxs-lookup"><span data-stu-id="ea4bd-143">boolean</span></span> | <span data-ttu-id="ea4bd-144">不明なルート証明書情報、無効な署名、失効した証明書、その他の疑いがある属性をチェックする WinVerifyTrust 関数の結果に基づいてファイルが信頼されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea4bd-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="ea4bd-145">ブール値</span><span class="sxs-lookup"><span data-stu-id="ea4bd-145">boolean</span></span> | <span data-ttu-id="ea4bd-146">ルート証明書の署名者が Microsoft であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="ea4bd-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="ea4bd-147">long</span><span class="sxs-lookup"><span data-stu-id="ea4bd-147">long</span></span> | <span data-ttu-id="ea4bd-148">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="ea4bd-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="ea4bd-149">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ea4bd-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="ea4bd-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="ea4bd-150">Related topics</span></span>
- [<span data-ttu-id="ea4bd-151">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="ea4bd-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ea4bd-152">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="ea4bd-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ea4bd-153">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="ea4bd-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ea4bd-154">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="ea4bd-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ea4bd-155">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="ea4bd-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ea4bd-156">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="ea4bd-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
