---
title: 高度なハンティング スキーマの DeviceFileCertificateInfo テーブル
description: 高度なハンティング スキーマの DeviceFileCertificateInfo テーブルのファイル署名情報について説明します。
keywords: 高度な検索、脅威の検出、サイバー脅威の検出、mdatp、microsoft Defender atp、wdatp 検索、クエリ、テレメトリ、スキーマ参照、kusto、table、column、data type、description、デジタル署名、証明書、ファイル署名、DeviceFileCertificateInfo
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 01/14/2020
ms.technology: mde
ms.openlocfilehash: f693c54828d8ede1d21167817f77b875ab5680ce
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499179"
---
# <a name="devicefilecertificateinfo"></a><span data-ttu-id="c1ac1-104">DeviceFileCertificateInfo</span><span class="sxs-lookup"><span data-stu-id="c1ac1-104">DeviceFileCertificateInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c1ac1-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="c1ac1-105">**Applies to:**</span></span>
- [<span data-ttu-id="c1ac1-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="c1ac1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="c1ac1-107">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="c1ac1-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c1ac1-108">無料試用版にサインアップします。</span><span class="sxs-lookup"><span data-stu-id="c1ac1-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="c1ac1-109">高度 `DeviceFileCertificateInfo` な検索スキーマ [の表](advanced-hunting-overview.md) には、ファイル署名証明書に関する情報が含まれている。</span><span class="sxs-lookup"><span data-stu-id="c1ac1-109">The `DeviceFileCertificateInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about file signing certificates.</span></span> <span data-ttu-id="c1ac1-110">次の表は、エンドポイント上のファイルで定期的に実行される証明書検証アクティビティから取得したデータを使用します。</span><span class="sxs-lookup"><span data-stu-id="c1ac1-110">This table uses data obtained from certificate verification activities regularly performed on files on endpoints.</span></span>

<span data-ttu-id="c1ac1-111">高度なハンティング スキーマの他のテーブルの詳細については、高度なハンティング [スキーマリファレンスを参照してください](advanced-hunting-schema-reference.md)。</span><span class="sxs-lookup"><span data-stu-id="c1ac1-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="c1ac1-112">列名</span><span class="sxs-lookup"><span data-stu-id="c1ac1-112">Column name</span></span> | <span data-ttu-id="c1ac1-113">データ型</span><span class="sxs-lookup"><span data-stu-id="c1ac1-113">Data type</span></span> | <span data-ttu-id="c1ac1-114">説明</span><span class="sxs-lookup"><span data-stu-id="c1ac1-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c1ac1-115">日付型</span><span class="sxs-lookup"><span data-stu-id="c1ac1-115">datetime</span></span> | <span data-ttu-id="c1ac1-116">イベントが記録された日付と時刻</span><span class="sxs-lookup"><span data-stu-id="c1ac1-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="c1ac1-117">文字列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-117">string</span></span> | <span data-ttu-id="c1ac1-118">サービス内のデバイスの一意の識別子</span><span class="sxs-lookup"><span data-stu-id="c1ac1-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="c1ac1-119">文字列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-119">string</span></span> | <span data-ttu-id="c1ac1-120">デバイスの完全修飾ドメイン名 (FQDN)</span><span class="sxs-lookup"><span data-stu-id="c1ac1-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `SHA1` | <span data-ttu-id="c1ac1-121">文字列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-121">string</span></span> | <span data-ttu-id="c1ac1-122">記録されたアクションが適用されたファイルの SHA-1</span><span class="sxs-lookup"><span data-stu-id="c1ac1-122">SHA-1 of the file that the recorded action was applied to</span></span> |
| `IsSigned` | <span data-ttu-id="c1ac1-123">boolean</span><span class="sxs-lookup"><span data-stu-id="c1ac1-123">boolean</span></span> | <span data-ttu-id="c1ac1-124">ファイルが署名されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c1ac1-124">Indicates whether the file is signed</span></span> |
| `SignatureType` | <span data-ttu-id="c1ac1-125">文字列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-125">string</span></span> | <span data-ttu-id="c1ac1-126">署名情報をファイル自体に埋め込みコンテンツとして読み取ったか、外部カタログ ファイルから読み取ったかを示します。</span><span class="sxs-lookup"><span data-stu-id="c1ac1-126">Indicates whether signature information was read as embedded content in the file itself or read from an external catalog file</span></span> |
| `Signer` | <span data-ttu-id="c1ac1-127">文字列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-127">string</span></span> | <span data-ttu-id="c1ac1-128">ファイルの署名者に関する情報</span><span class="sxs-lookup"><span data-stu-id="c1ac1-128">Information about the signer of the file</span></span> |
| `SignerHash` | <span data-ttu-id="c1ac1-129">文字列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-129">string</span></span> | <span data-ttu-id="c1ac1-130">署名者を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="c1ac1-130">Unique hash value identifying the signer</span></span> |
| `Issuer` | <span data-ttu-id="c1ac1-131">文字列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-131">string</span></span> | <span data-ttu-id="c1ac1-132">発行元証明機関 (CA) に関する情報</span><span class="sxs-lookup"><span data-stu-id="c1ac1-132">Information about the issuing certificate authority (CA)</span></span> |
| `IssuerHash` | <span data-ttu-id="c1ac1-133">文字列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-133">string</span></span> | <span data-ttu-id="c1ac1-134">発行元証明機関 (CA) を識別する一意のハッシュ値</span><span class="sxs-lookup"><span data-stu-id="c1ac1-134">Unique hash value identifying issuing certificate authority (CA)</span></span> |
| `CertificateSerialNumber` | <span data-ttu-id="c1ac1-135">文字列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-135">string</span></span> | <span data-ttu-id="c1ac1-136">発行元証明機関 (CA) に固有の証明書の識別子</span><span class="sxs-lookup"><span data-stu-id="c1ac1-136">Identifier for the certificate that is unique to the issuing certificate authority (CA)</span></span> |
| `CrlDistributionPointUrls` | <span data-ttu-id="c1ac1-137">文字列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-137">string</span></span> |  <span data-ttu-id="c1ac1-138">証明書と証明書失効リスト (CRL) を含むネットワーク共有の URL を示す JSON 配列</span><span class="sxs-lookup"><span data-stu-id="c1ac1-138">JSON array listing the URLs of network shares that contain certificates and certificate revocation lists (CRLs)</span></span> |
| `CertificateCreationTime` | <span data-ttu-id="c1ac1-139">日付型</span><span class="sxs-lookup"><span data-stu-id="c1ac1-139">datetime</span></span> | <span data-ttu-id="c1ac1-140">証明書が作成された日時</span><span class="sxs-lookup"><span data-stu-id="c1ac1-140">Date and time the certificate was created</span></span> |
| `CertificateExpirationTime` | <span data-ttu-id="c1ac1-141">日付型</span><span class="sxs-lookup"><span data-stu-id="c1ac1-141">datetime</span></span> | <span data-ttu-id="c1ac1-142">証明書の有効期限が設定されている日時</span><span class="sxs-lookup"><span data-stu-id="c1ac1-142">Date and time the certificate is set to expire</span></span> |
| `CertificateCountersignatureTime` | <span data-ttu-id="c1ac1-143">日付型</span><span class="sxs-lookup"><span data-stu-id="c1ac1-143">datetime</span></span> | <span data-ttu-id="c1ac1-144">証明書が署名された日時</span><span class="sxs-lookup"><span data-stu-id="c1ac1-144">Date and time the certificate was countersigned</span></span> |
| `IsTrusted` | <span data-ttu-id="c1ac1-145">boolean</span><span class="sxs-lookup"><span data-stu-id="c1ac1-145">boolean</span></span> | <span data-ttu-id="c1ac1-146">不明なルート証明書情報、無効な署名、失効した証明書、その他の疑いがある属性をチェックする WinVerifyTrust 関数の結果に基づいてファイルが信頼されているかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c1ac1-146">Indicates whether the file is trusted based on the results of the WinVerifyTrust function, which checks for unknown root certificate information, invalid signatures, revoked certificates, and other questionable attributes</span></span> |
| `IsRootSignerMicrosoft` | <span data-ttu-id="c1ac1-147">boolean</span><span class="sxs-lookup"><span data-stu-id="c1ac1-147">boolean</span></span> | <span data-ttu-id="c1ac1-148">ルート証明書の署名者が Microsoft であるかどうかを示します。</span><span class="sxs-lookup"><span data-stu-id="c1ac1-148">Indicates whether the signer of the root certificate is Microsoft</span></span> |
| `ReportId` | <span data-ttu-id="c1ac1-149">long</span><span class="sxs-lookup"><span data-stu-id="c1ac1-149">long</span></span> | <span data-ttu-id="c1ac1-150">繰り返しカウンターに基づくイベント識別子。</span><span class="sxs-lookup"><span data-stu-id="c1ac1-150">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c1ac1-151">一意のイベントを識別するには、この列を DeviceName 列と Timestamp 列と組み合わせて使用する必要があります。</span><span class="sxs-lookup"><span data-stu-id="c1ac1-151">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |


## <a name="related-topics"></a><span data-ttu-id="c1ac1-152">関連項目</span><span class="sxs-lookup"><span data-stu-id="c1ac1-152">Related topics</span></span>
- [<span data-ttu-id="c1ac1-153">高度な追求の概要</span><span class="sxs-lookup"><span data-stu-id="c1ac1-153">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c1ac1-154">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="c1ac1-154">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c1ac1-155">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="c1ac1-155">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
