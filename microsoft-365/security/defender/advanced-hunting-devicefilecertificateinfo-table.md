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
ms.openlocfilehash: 1f894f3fc8cff2113004ff9c9e34ec2ca0144799
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023215"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="d248a-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="d248a-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d248a-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="d248a-105">**Applies to:**</span></span>
- <span data-ttu-id="d248a-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d248a-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d248a-107">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d248a-107">Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="d248a-108">高度 `DeviceFileCertificateInfo` な検索スキーマ [の表](advanced-hunting-overview.md) には、ファイル署名証明書に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="d248a-108">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="d248a-109">次の表は、エンドポイント上のファイルで定期的に実行される証明書検証アクティビティから取得したデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="d248a-109">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="d248a-110">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="d248a-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d248a-111">列名</span><span class="sxs-lookup"><span data-stu-id="d248a-111">Column name</span></span> | <span data-ttu-id="d248a-112">データ型</span><span class="sxs-lookup"><span data-stu-id="d248a-112">Data type</span></span> | <span data-ttu-id="d248a-113">説明</span><span class="sxs-lookup"><span data-stu-id="d248a-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d248a-114">日付型</span><span class="sxs-lookup"><span data-stu-id="d248a-114">datetime</span></span> | <span data-ttu-id="d248a-115">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="d248a-115">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="d248a-116">文字列</span><span class="sxs-lookup"><span data-stu-id="d248a-116">string</span></span> | <span data-ttu-id="d248a-117">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="d248a-117">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="d248a-118">文字列</span><span class="sxs-lookup"><span data-stu-id="d248a-118">string</span></span> | <span data-ttu-id="d248a-119">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="d248a-119">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="d248a-120">文字列</span><span class="sxs-lookup"><span data-stu-id="d248a-120">string</span></span> | <span data-ttu-id="d248a-121">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="d248a-121">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="d248a-122">ブール値</span><span class="sxs-lookup"><span data-stu-id="d248a-122">boolean</span></span> | <span data-ttu-id="d248a-123">ファイルが署名されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d248a-123">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="d248a-124">文字列</span><span class="sxs-lookup"><span data-stu-id="d248a-124">string</span></span> | <span data-ttu-id="d248a-125">署名情報をファイル自体に埋め込みコンテンツとして読み取ったか、外部カタログ ファイルから読み取ったかを示します。</span><span class="sxs-lookup"><span data-stu-id="d248a-125">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="d248a-126">文字列</span><span class="sxs-lookup"><span data-stu-id="d248a-126">string</span></span> | <span data-ttu-id="d248a-127">ファイルの署名者に関する情報</span><span class="sxs-lookup"><span data-stu-id="d248a-127">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="d248a-128">文字列</span><span class="sxs-lookup"><span data-stu-id="d248a-128">string</span></span> | <span data-ttu-id="d248a-129">署名者を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="d248a-129">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="d248a-130">文字列</span><span class="sxs-lookup"><span data-stu-id="d248a-130">string</span></span> | <span data-ttu-id="d248a-131">発行元証明機関 (CA) に関する情報</span><span class="sxs-lookup"><span data-stu-id="d248a-131">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="d248a-132">文字列</span><span class="sxs-lookup"><span data-stu-id="d248a-132">string</span></span> | <span data-ttu-id="d248a-133">発行元証明機関 (CA) を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="d248a-133">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="d248a-134">文字列</span><span class="sxs-lookup"><span data-stu-id="d248a-134">string</span></span> | <span data-ttu-id="d248a-135">発行元証明機関 (CA) に固有の証明書の識別子</span><span class="sxs-lookup"><span data-stu-id="d248a-135">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="d248a-136">文字列</span><span class="sxs-lookup"><span data-stu-id="d248a-136">string</span></span> |  <span data-ttu-id="d248a-137">証明書と証明書失効リスト (CRL) を含むネットワーク共有の URL を示す JSON 配列</span><span class="sxs-lookup"><span data-stu-id="d248a-137">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="d248a-138">日付型</span><span class="sxs-lookup"><span data-stu-id="d248a-138">datetime</span></span> | <span data-ttu-id="d248a-139">証明書が作成された日時</span><span class="sxs-lookup"><span data-stu-id="d248a-139">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="d248a-140">日付型</span><span class="sxs-lookup"><span data-stu-id="d248a-140">datetime</span></span> | <span data-ttu-id="d248a-141">証明書の有効期限が設定されている日時</span><span class="sxs-lookup"><span data-stu-id="d248a-141">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="d248a-142">日付型</span><span class="sxs-lookup"><span data-stu-id="d248a-142">datetime</span></span> | <span data-ttu-id="d248a-143">証明書が署名された日時</span><span class="sxs-lookup"><span data-stu-id="d248a-143">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="d248a-144">ブール値</span><span class="sxs-lookup"><span data-stu-id="d248a-144">boolean</span></span> | <span data-ttu-id="d248a-145">不明なルート証明書情報、無効な署名、失効した証明書、その他の疑いがある属性をチェックする WinVerifyTrust 関数の結果に基づいてファイルが信頼されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d248a-145">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="d248a-146">ブール値</span><span class="sxs-lookup"><span data-stu-id="d248a-146">boolean</span></span> | <span data-ttu-id="d248a-147">ルート証明書の署名者が Microsoft であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="d248a-147">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="d248a-148">long</span><span class="sxs-lookup"><span data-stu-id="d248a-148">long</span></span> | <span data-ttu-id="d248a-149">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="d248a-149">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="d248a-150">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="d248a-150">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="d248a-151">関連項目</span><span class="sxs-lookup"><span data-stu-id="d248a-151">Related topics</span></span>
- [<span data-ttu-id="d248a-152">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="d248a-152">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d248a-153">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="d248a-153">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d248a-154">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="d248a-154">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d248a-155">デバイス、メール、アプリ、ID 全体で探す</span><span class="sxs-lookup"><span data-stu-id="d248a-155">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d248a-156">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="d248a-156">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d248a-157">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="d248a-157">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
