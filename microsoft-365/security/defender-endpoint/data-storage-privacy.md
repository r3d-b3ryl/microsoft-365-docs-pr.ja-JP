---
title: Microsoft Defender for Endpoint データストレージとプライバシー
description: Microsoft Defender for Endpoint が収集するプライバシーとデータを処理する方法について説明します。
keywords: Microsoft Defender for Endpoint, data storage and privacy, storage, privacy, licensing, geolocation, data retention, data
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2279045093ebfac4a7eb4544a3e0c137c08c9c0c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935391"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a><span data-ttu-id="16ca3-104">Microsoft Defender for Endpoint データストレージとプライバシー</span><span class="sxs-lookup"><span data-stu-id="16ca3-104">Microsoft Defender for Endpoint data storage and privacy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="16ca3-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="16ca3-105">**Applies to:**</span></span>
- [<span data-ttu-id="16ca3-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="16ca3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="16ca3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="16ca3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="16ca3-108">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="16ca3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="16ca3-109">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="16ca3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="16ca3-110">このセクションでは、Defender for Endpoint のプライバシーとデータ処理に関してよく寄せられる質問について説明します。</span><span class="sxs-lookup"><span data-stu-id="16ca3-110">This section covers some of the most frequently asked questions regarding privacy and data handling for Defender for Endpoint.</span></span>
> [!NOTE]
> <span data-ttu-id="16ca3-111">このドキュメントでは、Defender for Endpoint に関連するデータストレージとプライバシーの詳細について説明します。</span><span class="sxs-lookup"><span data-stu-id="16ca3-111">This document explains the data storage and privacy details related to Defender for Endpoint.</span></span> <span data-ttu-id="16ca3-112">Defender for Endpoint および他の製品およびサービス (Microsoft Defender ウイルス対策 および Windows 10に関する詳細については[、「Microsoft Privacy Statement」を参照してください](https://go.microsoft.com/fwlink/?linkid=827576)。</span><span class="sxs-lookup"><span data-stu-id="16ca3-112">For more information related to Defender for Endpoint and other products and services like Microsoft Defender Antivirus and Windows 10, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=827576).</span></span> <span data-ttu-id="16ca3-113">詳細については[、「Windows 10 FAQ」](https://go.microsoft.com/fwlink/?linkid=827577)を参照してください。</span><span class="sxs-lookup"><span data-stu-id="16ca3-113">See also [Windows 10 privacy FAQ](https://go.microsoft.com/fwlink/?linkid=827577) for more information.</span></span>


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a><span data-ttu-id="16ca3-114">Microsoft Defender for Endpoint が収集するデータは何ですか?</span><span class="sxs-lookup"><span data-stu-id="16ca3-114">What data does Microsoft Defender for Endpoint collect?</span></span>

<span data-ttu-id="16ca3-115">Microsoft Defender for Endpoint は、管理、追跡、およびレポートの目的でサービスに固有の、構成済みのデバイスから、サービス固有の専用テナントおよび分離テナントに情報を収集して保存します。</span><span class="sxs-lookup"><span data-stu-id="16ca3-115">Microsoft Defender for Endpoint will collect and store information from your configured devices in a customer dedicated and segregated tenant specific to the service for administration, tracking, and reporting purposes.</span></span> 

<span data-ttu-id="16ca3-116">収集される情報には、ファイル データ (ファイル名、サイズ、ハッシュなど)、プロセス データ (実行中のプロセス、ハッシュ)、レジストリ データ、ネットワーク接続データ (ホスト IP とポート)、デバイスの詳細 (デバイス識別子、名前、オペレーティング システムのバージョンなど) が含まれます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-116">Information collected includes file data (such as file names, sizes, and hashes), process data (running processes, hashes), registry data, network connection data (host IPs and ports), and device details (such as device identifiers, names, and the operating system version).</span></span>

<span data-ttu-id="16ca3-117">Microsoft は、このデータをセキュリティで保護Microsoft Azure、Microsoft のプライバシープラクティスと Microsoft Trust Center ポリシーに従[って管理します](https://go.microsoft.com/fwlink/?linkid=827578)。</span><span class="sxs-lookup"><span data-stu-id="16ca3-117">Microsoft stores this data securely in Microsoft Azure and maintains it in accordance with Microsoft privacy practices and [Microsoft Trust Center policies](https://go.microsoft.com/fwlink/?linkid=827578).</span></span>

<span data-ttu-id="16ca3-118">このデータを使用すると、Defender for Endpoint は次の操作を実行できます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-118">This data enables Defender for Endpoint to:</span></span>
- <span data-ttu-id="16ca3-119">組織内の攻撃の指標 (IOA) を積極的に特定する</span><span class="sxs-lookup"><span data-stu-id="16ca3-119">Proactively identify indicators of attack (IOAs) in your organization</span></span>
- <span data-ttu-id="16ca3-120">攻撃の可能性が検出された場合にアラートを生成する</span><span class="sxs-lookup"><span data-stu-id="16ca3-120">Generate alerts if a possible attack was detected</span></span>
- <span data-ttu-id="16ca3-121">ネットワークからの脅威信号に関連するデバイス、ファイル、URL を確認してセキュリティ操作を提供し、ネットワーク上のセキュリティ脅威の存在を調査し、調査することができます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-121">Provide your security operations with a view into devices, files, and URLs related to threat signals from your network, enabling you to investigate and explore the presence of security threats on the network.</span></span>

<span data-ttu-id="16ca3-122">Microsoft は広告にデータを使用しない。</span><span class="sxs-lookup"><span data-stu-id="16ca3-122">Microsoft does not use your data for advertising.</span></span>

## <a name="data-protection-and-encryption"></a><span data-ttu-id="16ca3-123">データ保護と暗号化</span><span class="sxs-lookup"><span data-stu-id="16ca3-123">Data protection and encryption</span></span>
<span data-ttu-id="16ca3-124">Defender for Endpoint サービスは、最新のデータ保護テクノロジを利用し、最新のインフラストラクチャに基Microsoft Azureします。</span><span class="sxs-lookup"><span data-stu-id="16ca3-124">The Defender for Endpoint service utilizes state of the art data protection technologies which are based on Microsoft Azure infrastructure.</span></span> 

<span data-ttu-id="16ca3-125">弊社のサービスが管理するデータ保護に関連するさまざまな側面があります。</span><span class="sxs-lookup"><span data-stu-id="16ca3-125">There are various aspects relevant to data protection that our service takes care of.</span></span> <span data-ttu-id="16ca3-126">暗号化は最も重要な 1 つであり、保存時のデータ暗号化、飛行中の暗号化、Key Vault によるキー管理が含まれます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-126">Encryption is one of the most critical and it includes data encryption at rest, encryption in flight, and key management with Key Vault.</span></span> <span data-ttu-id="16ca3-127">Defender for Endpoint サービスで使用される他のテクノロジの詳細については、「Azure 暗号化の [概要」を参照してください](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)。</span><span class="sxs-lookup"><span data-stu-id="16ca3-127">For more information on other technologies used by the Defender for Endpoint service, see [Azure encryption overview](https://docs.microsoft.com/azure/security/security-azure-encryption-overview).</span></span> 

<span data-ttu-id="16ca3-128">すべてのシナリオで、データは最小で 256 ビット [の AES 暗号化](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) を使用して暗号化されます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-128">In all scenarios, data is encrypted using 256-bit [AES encryption](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) at the minimum.</span></span>


## <a name="data-storage-location"></a><span data-ttu-id="16ca3-129">データの保存場所</span><span class="sxs-lookup"><span data-stu-id="16ca3-129">Data storage location</span></span>

<span data-ttu-id="16ca3-130">Defender for Endpoint は、Microsoft Azure、英国、または米国のデータセンターで動作します。</span><span class="sxs-lookup"><span data-stu-id="16ca3-130">Defender for Endpoint operates in the Microsoft Azure datacenters in the European Union, the United Kingdom, or in the United States.</span></span> <span data-ttu-id="16ca3-131">サービスによって収集された顧客データは、(a) プロビジョニング中に特定されたテナントの地理的位置、または (b) Defender for Endpoint が別の Microsoft オンライン サービスを使用してそのようなデータを処理する場合、その他のオンライン サービスのデータストレージ ルールで定義される地理的位置に格納されます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-131">Customer data collected by the service may be stored in: (a) the geo-location of the tenant as identified during provisioning or, (b) if Defender for Endpoint uses another Microsoft online service to process such data, the geolocation as defined by the data storage rules of that other online service.</span></span>

<span data-ttu-id="16ca3-132">仮名化された形式の顧客データは、米国の中央ストレージおよび処理システムに保存される場合があります。</span><span class="sxs-lookup"><span data-stu-id="16ca3-132">Customer data in pseudonymized form may also be stored in the central storage and processing systems in the United States.</span></span>

<span data-ttu-id="16ca3-133">構成が完了すると、データの保存場所を変更できません。</span><span class="sxs-lookup"><span data-stu-id="16ca3-133">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="16ca3-134">これにより、データが存在する地理的な場所を積極的に選択することで、コンプライアンス リスクを最小限に抑える便利な方法が提供されます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-134">This provides a convenient way to minimize compliance risk by actively selecting the geographic locations where your data will reside.</span></span> 

## <a name="is-my-data-isolated-from-other-customer-data"></a><span data-ttu-id="16ca3-135">自分のデータは他の顧客データから分離されていますか?</span><span class="sxs-lookup"><span data-stu-id="16ca3-135">Is my data isolated from other customer data?</span></span>
<span data-ttu-id="16ca3-136">はい、データはアクセス認証と顧客識別子に基づく論理的な分離によって分離されます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-136">Yes, your data is isolated through access authentication and logical segregation based on customer identifier.</span></span> <span data-ttu-id="16ca3-137">各顧客は、Microsoft が提供する独自の組織および汎用データから収集されたデータにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-137">Each customer can only access data collected from its own organization and generic data that Microsoft provides.</span></span>

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a><span data-ttu-id="16ca3-138">Microsoft は、悪意のあるインサイダーアクティビティや特権の高い役割の悪用を防止する方法を説明します。</span><span class="sxs-lookup"><span data-stu-id="16ca3-138">How does Microsoft prevent malicious insider activities and abuse of high privilege roles?</span></span>

<span data-ttu-id="16ca3-139">Microsoft の開発者と管理者は、設計上、サービスの運用と進化のために割り当てられた職務を遂行するのに十分な特権を与えら た。</span><span class="sxs-lookup"><span data-stu-id="16ca3-139">Microsoft developers and administrators have, by design, been given sufficient privileges to carry out their assigned duties to operate and evolve the service.</span></span> <span data-ttu-id="16ca3-140">Microsoft では、承認されていない開発者や管理活動から保護するために、次のメカニズムを含む予防、探偵、および反応性の制御の組み合わせを展開しています。</span><span class="sxs-lookup"><span data-stu-id="16ca3-140">Microsoft deploys combinations of preventive, detective, and reactive controls including the following mechanisms to help protect against unauthorized developer and/or administrative activity:</span></span>

- <span data-ttu-id="16ca3-141">機密データへの厳しいアクセス制御</span><span class="sxs-lookup"><span data-stu-id="16ca3-141">Tight access control to sensitive data</span></span>
- <span data-ttu-id="16ca3-142">悪意のあるアクティビティの独立した検出を大幅に強化するコントロールの組み合わせ</span><span class="sxs-lookup"><span data-stu-id="16ca3-142">Combinations of controls that greatly enhance independent detection of malicious activity</span></span>
- <span data-ttu-id="16ca3-143">複数のレベルの監視、ログ、およびレポート</span><span class="sxs-lookup"><span data-stu-id="16ca3-143">Multiple levels of monitoring, logging, and reporting</span></span>

<span data-ttu-id="16ca3-144">さらに、Microsoft は特定の運用担当者のバックグラウンド検証チェックを実施し、バックグラウンド検証のレベルに応じてアプリケーション、システム、およびネットワーク インフラストラクチャへのアクセスを制限します。</span><span class="sxs-lookup"><span data-stu-id="16ca3-144">Additionally, Microsoft conducts background verification checks of certain operations personnel, and limits access to applications, systems, and network infrastructure in proportion to the level of background verification.</span></span> <span data-ttu-id="16ca3-145">運用担当者は、業務の遂行中に顧客のアカウントまたは関連情報にアクセスする必要がある場合、正式なプロセスに従います。</span><span class="sxs-lookup"><span data-stu-id="16ca3-145">Operations personnel follow a formal process when they are required to access a customer’s account or related information in the performance of their duties.</span></span>

<span data-ttu-id="16ca3-146">Microsoft Azure Government データ センターに展開されるサービスのデータへのアクセスは、FedRAMP、NIST 800.171 (DIB)、ITAR、IRS 1075、DoD L4、CJIS など、特定の政府の規制および要件の対象となるデータの処理を承認された運用担当者にのみ付与されます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-146">Access to data for services deployed in Microsoft Azure Government data centers is only granted to operating personnel who have been screened and approved to handle data that is subject to certain government regulations and requirements, such as FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4, and CJIS.</span></span>


## <a name="is-data-shared-with-other-customers"></a><span data-ttu-id="16ca3-147">データは他の顧客と共有されていますか?</span><span class="sxs-lookup"><span data-stu-id="16ca3-147">Is data shared with other customers?</span></span>
<span data-ttu-id="16ca3-148">いいえ。</span><span class="sxs-lookup"><span data-stu-id="16ca3-148">No.</span></span> <span data-ttu-id="16ca3-149">顧客データは他の顧客から分離され、共有されません。</span><span class="sxs-lookup"><span data-stu-id="16ca3-149">Customer data is isolated from other customers and is not shared.</span></span> <span data-ttu-id="16ca3-150">ただし、Microsoft の処理に起因するデータ、および顧客固有のデータを含むデータに関する分析情報は、他の顧客と共有される場合があります。</span><span class="sxs-lookup"><span data-stu-id="16ca3-150">However, insights on the data resulting from Microsoft processing, and which don’t contain any customer-specific data, might be shared with other customers.</span></span> <span data-ttu-id="16ca3-151">各顧客は、Microsoft が提供する独自の組織および汎用データから収集されたデータにのみアクセスできます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-151">Each customer can only access data collected from its own organization and generic data that Microsoft provides.</span></span>

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a><span data-ttu-id="16ca3-152">Microsoft は自分のデータを保存する期間を指定します。</span><span class="sxs-lookup"><span data-stu-id="16ca3-152">How long will Microsoft store my data?</span></span> <span data-ttu-id="16ca3-153">Microsoft のデータ保持ポリシーとは</span><span class="sxs-lookup"><span data-stu-id="16ca3-153">What is Microsoft’s data retention policy?</span></span>
<span data-ttu-id="16ca3-154">**サービスオンボーディング時**</span><span class="sxs-lookup"><span data-stu-id="16ca3-154">**At service onboarding**</span></span><br>
<span data-ttu-id="16ca3-155">既定では、データは 180 日間保持されます。ただし、データのデータ保持ポリシーを指定できます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-155">By default, data is retained for 180 days; however, you can specify the data retention policy for your data.</span></span> <span data-ttu-id="16ca3-156">これにより、Window Defender for Endpoint がデータを保存する期間が決されます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-156">This determines how long Window Defender for Endpoint will store your data.</span></span> <span data-ttu-id="16ca3-157">会社の規制コンプライアンスニーズを満たすために、1 か月から 6 か月の範囲で柔軟に選択できます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-157">There’s a flexibility of choosing in the range of one month to six months to meet your company’s regulatory compliance needs.</span></span>

<span data-ttu-id="16ca3-158">**契約の終了または有効期限時**</span><span class="sxs-lookup"><span data-stu-id="16ca3-158">**At contract termination or expiration**</span></span><br>
<span data-ttu-id="16ca3-159">ライセンスが猶予期間または中断モードの間、データは保持され、利用できます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-159">Your data will be kept and will be available to you while the license is under grace period or suspended mode.</span></span> <span data-ttu-id="16ca3-160">この期間の終わりに、そのデータは Microsoft のシステムから消去され、契約の終了または有効期限から 180 日以内に回復不能になります。</span><span class="sxs-lookup"><span data-stu-id="16ca3-160">At the end of this period, that data will be erased from Microsoft’s systems to make it unrecoverable, no later than 180 days from contract termination or expiration.</span></span>

<span data-ttu-id="16ca3-161">**高度なハンティング データ**</span><span class="sxs-lookup"><span data-stu-id="16ca3-161">**Advanced Hunting data**</span></span><br>
<span data-ttu-id="16ca3-162">高度な捜索は、クエリ ベースの脅威の捜索ツールで、最大 30 日間のロー データを検索できます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-162">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span>


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a><span data-ttu-id="16ca3-163">Microsoft は、規制コンプライアンスの維持に役立ちますか?</span><span class="sxs-lookup"><span data-stu-id="16ca3-163">Can Microsoft help us maintain regulatory compliance?</span></span>

<span data-ttu-id="16ca3-164">Microsoft は、Microsoft のセキュリティおよびコンプライアンス プログラムに関する詳細な情報 (監査レポートやコンプライアンス パッケージなど) を提供し、お客様が Defender for Endpoint サービスを独自の法的および規制上の要件に対して評価するのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-164">Microsoft provides customers with detailed information about Microsoft's security and compliance programs, including audit reports and compliance packages, to help customers assess Defender for Endpoint services against their own legal and regulatory requirements.</span></span> <span data-ttu-id="16ca3-165">Defender for Endpoint は、ISO、SOC、FedRAMP High、PCI などの多くの認定を取得し、国内、地域、業界固有の追加の認定を引き続き追求しています。</span><span class="sxs-lookup"><span data-stu-id="16ca3-165">Defender for Endpoint has achieved a number of certifications including ISO, SOC, FedRAMP High, and PCI and continues to pursue additional national, regional and industry-specific certifications.</span></span>

<span data-ttu-id="16ca3-166">Microsoft は、コンプライアンスに準拠した個別に検証されたサービスを顧客に提供することで、お客様が実行するインフラストラクチャとアプリケーションのコンプライアンスを簡単に実現できます。</span><span class="sxs-lookup"><span data-stu-id="16ca3-166">By providing customers with compliant, independently verified services, Microsoft makes it easier for customers to achieve compliance for the infrastructure and applications they run.</span></span>

<span data-ttu-id="16ca3-167">Defender for Endpoint 認定レポートの詳細については [、「Microsoft Trust Center」を参照してください](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="16ca3-167">For more information on the Defender for Endpoint certification reports, see [Microsoft Trust Center](https://servicetrust.microsoft.com/).</span></span> 

><span data-ttu-id="16ca3-168">Defender for Endpoint を体験してみませんか?</span><span class="sxs-lookup"><span data-stu-id="16ca3-168">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="16ca3-169">無料試用版にサインアップしてください。</span><span class="sxs-lookup"><span data-stu-id="16ca3-169">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
