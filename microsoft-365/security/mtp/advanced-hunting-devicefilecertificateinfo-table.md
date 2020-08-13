---
title: 高度な検索スキーマの DeviceFileCertificateInfo テーブル
description: 高度な検索スキーマの DeviceFileCertificateInfo テーブルにあるファイルの署名情報について説明します。
keywords: 高度な検索、脅威の探し、サイバー脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、スキーマ参照、kusto、table、column、data type、digital signature、certificate、file signature、DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 33f9c726839f17afbb935c6d028cc4eaa5b74843
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649453"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="003f4-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="003f4-104">DeviceFileCertificateInfo</span></span>

<span data-ttu-id="003f4-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="003f4-105">**Applies to:**</span></span>
- <span data-ttu-id="003f4-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="003f4-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="003f4-107">`DeviceFileCertificateInfo`[高度な](advanced-hunting-overview.md)検索スキーマの表には、ファイル署名証明書に関する情報が含まれています。</span><span class="sxs-lookup"><span data-stu-id="003f4-107">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="003f4-108">この表では、エンドポイントのファイルで定期的に実行される証明書の検証アクティビティから取得したデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="003f4-108">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="003f4-109">高度な捜索スキーマのその他のテーブルの詳細については、「[高度な捜索のリファレンス](advanced-hunting-schema-tables.md)」 を参照してください。</span><span class="sxs-lookup"><span data-stu-id="003f4-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="003f4-110">列名</span><span class="sxs-lookup"><span data-stu-id="003f4-110">Column name</span></span> | <span data-ttu-id="003f4-111">データ型</span><span class="sxs-lookup"><span data-stu-id="003f4-111">Data type</span></span> | <span data-ttu-id="003f4-112">説明</span><span class="sxs-lookup"><span data-stu-id="003f4-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="003f4-113">日付型</span><span class="sxs-lookup"><span data-stu-id="003f4-113">datetime</span></span> | <span data-ttu-id="003f4-114">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="003f4-114">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="003f4-115">string</span><span class="sxs-lookup"><span data-stu-id="003f4-115">string</span></span> | <span data-ttu-id="003f4-116">コンピューターの一意識別子</span><span class="sxs-lookup"><span data-stu-id="003f4-116">Unique identifier for the machine in the service</span></span> |
| `DeviceName` | <span data-ttu-id="003f4-117">string</span><span class="sxs-lookup"><span data-stu-id="003f4-117">string</span></span> | <span data-ttu-id="003f4-118">コンピューターの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="003f4-118">Fully qualified domain name (FQDN) of the machine</span></span> |
| `SHA1` | <span data-ttu-id="003f4-119">文字列</span><span class="sxs-lookup"><span data-stu-id="003f4-119">string</span></span> | <span data-ttu-id="003f4-120">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="003f4-120">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="003f4-121">ブール値</span><span class="sxs-lookup"><span data-stu-id="003f4-121">boolean</span></span> | <span data-ttu-id="003f4-122">ファイルが署名されているかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="003f4-122">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="003f4-123">string</span><span class="sxs-lookup"><span data-stu-id="003f4-123">string</span></span> | <span data-ttu-id="003f4-124">署名情報がファイル自体の埋め込みコンテンツとして読み取られたか、外部カタログファイルから読み取られたかを示します</span><span class="sxs-lookup"><span data-stu-id="003f4-124">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="003f4-125">string</span><span class="sxs-lookup"><span data-stu-id="003f4-125">string</span></span> | <span data-ttu-id="003f4-126">ファイルの署名者に関する情報</span><span class="sxs-lookup"><span data-stu-id="003f4-126">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="003f4-127">string</span><span class="sxs-lookup"><span data-stu-id="003f4-127">string</span></span> | <span data-ttu-id="003f4-128">署名者を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="003f4-128">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="003f4-129">string</span><span class="sxs-lookup"><span data-stu-id="003f4-129">string</span></span> | <span data-ttu-id="003f4-130">発行元の証明機関 (CA) に関する情報</span><span class="sxs-lookup"><span data-stu-id="003f4-130">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="003f4-131">string</span><span class="sxs-lookup"><span data-stu-id="003f4-131">string</span></span> | <span data-ttu-id="003f4-132">発行証明機関 (CA) を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="003f4-132">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="003f4-133">string</span><span class="sxs-lookup"><span data-stu-id="003f4-133">string</span></span> | <span data-ttu-id="003f4-134">発行元の証明機関 (CA) に固有の証明書の識別子</span><span class="sxs-lookup"><span data-stu-id="003f4-134">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="003f4-135">string</span><span class="sxs-lookup"><span data-stu-id="003f4-135">string</span></span> |  <span data-ttu-id="003f4-136">証明書と証明書失効リスト (Crl) を含むネットワーク共有の Url を一覧表示する JSON 配列</span><span class="sxs-lookup"><span data-stu-id="003f4-136">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="003f4-137">日付型</span><span class="sxs-lookup"><span data-stu-id="003f4-137">datetime</span></span> | <span data-ttu-id="003f4-138">証明書が作成された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="003f4-138">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="003f4-139">日付型</span><span class="sxs-lookup"><span data-stu-id="003f4-139">datetime</span></span> | <span data-ttu-id="003f4-140">証明書が期限切れに設定された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="003f4-140">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="003f4-141">日付型</span><span class="sxs-lookup"><span data-stu-id="003f4-141">datetime</span></span> | <span data-ttu-id="003f4-142">証明書が副署名された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="003f4-142">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="003f4-143">ブール値</span><span class="sxs-lookup"><span data-stu-id="003f4-143">boolean</span></span> | <span data-ttu-id="003f4-144">WinVerifyTrust 関数の結果に基づいてファイルが信頼されているかどうかを示します。この関数は、不明なルート証明書情報、無効な署名、失効した証明書、およびその他の疑わしい属性をチェックします。</span><span class="sxs-lookup"><span data-stu-id="003f4-144">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="003f4-145">ブール値</span><span class="sxs-lookup"><span data-stu-id="003f4-145">boolean</span></span> | <span data-ttu-id="003f4-146">ルート証明書の署名者が Microsoft であるかどうかを示します</span><span class="sxs-lookup"><span data-stu-id="003f4-146">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="003f4-147">long</span><span class="sxs-lookup"><span data-stu-id="003f4-147">long</span></span> | <span data-ttu-id="003f4-148">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="003f4-148">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="003f4-149">一意のイベントを識別するには、この列を DeviceName および Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="003f4-149">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> | 

## <a name="related-topics"></a><span data-ttu-id="003f4-150">関連項目</span><span class="sxs-lookup"><span data-stu-id="003f4-150">Related topics</span></span>
- [<span data-ttu-id="003f4-151">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="003f4-151">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="003f4-152">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="003f4-152">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="003f4-153">共有クエリを使用する</span><span class="sxs-lookup"><span data-stu-id="003f4-153">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="003f4-154">デバイス、メール、アプリ、および id の間でのハント</span><span class="sxs-lookup"><span data-stu-id="003f4-154">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="003f4-155">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="003f4-155">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="003f4-156">クエリのベスト プラクティスを適用する</span><span class="sxs-lookup"><span data-stu-id="003f4-156">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
