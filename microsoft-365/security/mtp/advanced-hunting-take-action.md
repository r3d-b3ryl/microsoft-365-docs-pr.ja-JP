---
title: Microsoft の脅威保護で高度な検索クエリ結果に対してアクションを実行する
description: 高度な検索のクエリ結果の脅威と影響を受ける資産を迅速に解決する
keywords: 高度な検索、脅威の探し、サイバーの脅威の検索、microsoft threat protection、microsoft 365、mtp、m365、search、query、テレメトリ、take action
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7250feffa69cc1a6cc37908a599dff0fab6c5e6c
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429657"
---
# <a name="take-action-on-advanced-hunting-query-results"></a><span data-ttu-id="2e4fa-104">高度な検索クエリ結果に対してアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="2e4fa-104">Take action on advanced hunting query results</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="2e4fa-105">**適用対象:**</span><span class="sxs-lookup"><span data-stu-id="2e4fa-105">**Applies to:**</span></span>
- <span data-ttu-id="2e4fa-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="2e4fa-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="2e4fa-107">強力で包括的なアクションオプションを使用することにより、 [高度な](advanced-hunting-overview.md) 検索によって検出された脅威や、侵害された資産に対処することができます。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-107">You can quickly contain threats or address compromised assets that you find in [advanced hunting](advanced-hunting-overview.md) using powerful and comprehensive action options.</span></span> <span data-ttu-id="2e4fa-108">これらのオプションを使用すると、次のことができます。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-108">With these options, you can:</span></span>

- <span data-ttu-id="2e4fa-109">デバイスでさまざまなアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="2e4fa-109">Take various actions on devices</span></span>
- <span data-ttu-id="2e4fa-110">ファイルの検疫</span><span class="sxs-lookup"><span data-stu-id="2e4fa-110">Quarantine files</span></span>

## <a name="required-permissions"></a><span data-ttu-id="2e4fa-111">必要なアクセス許可</span><span class="sxs-lookup"><span data-stu-id="2e4fa-111">Required permissions</span></span>
<span data-ttu-id="2e4fa-112">高度な検索を通じてアクションを実行できるようにするには、 [デバイスで修復操作を送信するためのアクセス許可](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options)を持つ MICROSOFT Defender ATP の役割が必要です。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-112">To be able to take action through advanced hunting, you need a role in Microsoft Defender ATP with [permissions to submit remediation actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options).</span></span> <span data-ttu-id="2e4fa-113">アクションを実行できない場合は、次のアクセス許可の取得について全体管理者に問い合わせてください。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-113">If you can't take action, contact a global administrator about getting the following permission:</span></span>

<span data-ttu-id="2e4fa-114">*アクティブな修復アクション > 脅威と脆弱性の管理-修復処理*</span><span class="sxs-lookup"><span data-stu-id="2e4fa-114">*Active remediation actions > Threat and vulnerability management - Remediation handling*</span></span>

## <a name="take-various-actions-on-devices"></a><span data-ttu-id="2e4fa-115">デバイスでさまざまなアクションを実行する</span><span class="sxs-lookup"><span data-stu-id="2e4fa-115">Take various actions on devices</span></span>
<span data-ttu-id="2e4fa-116">クエリ結果の列で識別されるデバイスに対して、次の操作を行うことができ `DeviceId` ます。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-116">You can take the following actions on devices identified by the `DeviceId` column in you query results:</span></span>

- <span data-ttu-id="2e4fa-117">影響を受けるデバイスを分離して感染を抑制するか、laterally の移行を防ぐ</span><span class="sxs-lookup"><span data-stu-id="2e4fa-117">Isolate affected devices to contain an infection or prevent attacks from moving laterally</span></span>
- <span data-ttu-id="2e4fa-118">調査パッケージを収集して、より法的情報を入手する</span><span class="sxs-lookup"><span data-stu-id="2e4fa-118">Collect investigation package to obtain more forensic information</span></span>
- <span data-ttu-id="2e4fa-119">ウイルス対策スキャンを実行して、最新のセキュリティインテリジェンス更新を使用して脅威を見つけて削除する</span><span class="sxs-lookup"><span data-stu-id="2e4fa-119">Run an antivirus scan to find and remove threats using the latest security intelligence updates</span></span>
- <span data-ttu-id="2e4fa-120">デバイスとその他の影響を受けるデバイス上の脅威をチェックおよび修復するための自動化された調査を開始します。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-120">Initiate an automated investigation to check and remediate threats on the device and possibly other affected devices</span></span>
- <span data-ttu-id="2e4fa-121">Microsoft 署名済みの実行可能ファイルのみにアプリの実行を制限し、マルウェアまたは他の信頼されていない実行可能ファイルからの後続の脅威を防止します。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-121">Restrict app execution to only Microsoft-signed executable files, preventing subsequent threat activity through malware or other untrusted executables</span></span>

<span data-ttu-id="2e4fa-122">Microsoft Defender ATP を使用してこれらの応答アクションを実行する方法の詳細については、「 [デバイスに対する応答アクションについて](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-122">To learn more about how these response actions are performed through Microsoft Defender ATP, [read about response actions on devices](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).</span></span>
   
## <a name="quarantine-files"></a><span data-ttu-id="2e4fa-123">ファイルの検疫</span><span class="sxs-lookup"><span data-stu-id="2e4fa-123">Quarantine files</span></span>
<span data-ttu-id="2e4fa-124">*検疫*アクションをファイルに展開して、検出時に自動的に検疫されるようにすることができます。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-124">You can deploy the *quarantine* action on files so that they are automatically quarantined when encountered.</span></span> <span data-ttu-id="2e4fa-125">このアクションを選択する場合、次の列から選択して、クエリ結果のどのファイルを検疫するかを指定できます。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-125">When selecting this action, you can choose between the following columns to identify which files in your query results to quarantine:</span></span>

- <span data-ttu-id="2e4fa-126">`SHA1` —最も高度な検索テーブルの場合、これは、記録された操作の影響を受けたファイルの SHA-1 です。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-126">`SHA1` — In most advanced hunting tables, this is the SHA-1 of the file that was affected by the recorded action.</span></span> <span data-ttu-id="2e4fa-127">たとえば、ファイルがコピーされた場合、これはコピーされたファイルになります。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-127">For example, if a file was copied, this would be the copied file.</span></span>
- <span data-ttu-id="2e4fa-128">`InitiatingProcessSHA1` —最も高度な検索テーブルの場合、これは、記録されたアクションを開始するためのファイルです。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-128">`InitiatingProcessSHA1` — In most advanced hunting tables, this is the file responsible for initiating the recorded action.</span></span> <span data-ttu-id="2e4fa-129">たとえば、子プロセスが起動された場合、これは親プロセスになります。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-129">For example, if a child process was launched, this would be the parent process.</span></span> 
- <span data-ttu-id="2e4fa-130">`SHA256` —これは、列で指定されたファイルに対応する SHA-1 256 に相当し `SHA1` ます。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-130">`SHA256` — This is the SHA-256 equivalent of the file identified by the `SHA1` column.</span></span>
- <span data-ttu-id="2e4fa-131">`InitiatingProcessSHA256` —これは、列で指定されたファイルに対応する SHA-1 256 に相当し `InitiatingProcessSHA1` ます。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-131">`InitiatingProcessSHA256` — This is the SHA-256 equivalent of the file identified by the `InitiatingProcessSHA1` column.</span></span>

<span data-ttu-id="2e4fa-132">検疫アクションの実行方法とファイルの復元方法の詳細については、「 [ファイルに対する応答アクションについ](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)て」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-132">To learn more about how quarantine actions are taken and how files can be restored, [read about response actions on files](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).</span></span>

>[!NOTE]
><span data-ttu-id="2e4fa-133">ファイルを検索し、それらを検疫するために、クエリ結果には `DeviceId` デバイス識別子として値も含める必要があります。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-133">To locate files and quarantine them, the query results should also include `DeviceId` values as device identifiers.</span></span>  

## <a name="take-action"></a><span data-ttu-id="2e4fa-134">アクションを実行する</span><span class="sxs-lookup"><span data-stu-id="2e4fa-134">Take action</span></span>
<span data-ttu-id="2e4fa-135">上記の操作のいずれかを実行するには、クエリ結果で1つ以上のレコードを選択し、[ **アクションを実行**] を選択します。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-135">To take any of the described actions, select one or more records in your query results and then select **Take actions**.</span></span> <span data-ttu-id="2e4fa-136">ウィザードに従って、優先する操作を選択して送信するプロセスを実行できます。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-136">A wizard will guide you through the process of selecting and then submitting your preferred actions.</span></span>

![レコードを検査するためのパネルがある、選択されたレコードのイメージ](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a><span data-ttu-id="2e4fa-138">実行されたアクションを確認する</span><span class="sxs-lookup"><span data-stu-id="2e4fa-138">Review actions taken</span></span>
<span data-ttu-id="2e4fa-139">各アクションは、アクション**センター**の[action center](mtp-action-center.md)  >  **履歴**([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)) の下にあるアクションセンターに個別に記録されます。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-139">Each action is individually recorded in the [action center](mtp-action-center.md) under **Action center** > **History** ([security.microsoft.com/action-center/history](https://security.microsoft.com/action-center/history)).</span></span> <span data-ttu-id="2e4fa-140">アクションセンターに移動して、各アクションの状態を確認します。</span><span class="sxs-lookup"><span data-stu-id="2e4fa-140">Go to the action center to check the status of each action.</span></span>
 
## <a name="related-topics"></a><span data-ttu-id="2e4fa-141">関連項目</span><span class="sxs-lookup"><span data-stu-id="2e4fa-141">Related topics</span></span>
- [<span data-ttu-id="2e4fa-142">高度な検出の概要</span><span class="sxs-lookup"><span data-stu-id="2e4fa-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="2e4fa-143">クエリ言語の説明</span><span class="sxs-lookup"><span data-stu-id="2e4fa-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="2e4fa-144">クエリ結果を操作する</span><span class="sxs-lookup"><span data-stu-id="2e4fa-144">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="2e4fa-145">スキーマを理解する</span><span class="sxs-lookup"><span data-stu-id="2e4fa-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="2e4fa-146">アクションセンターの概要</span><span class="sxs-lookup"><span data-stu-id="2e4fa-146">Action center overview</span></span>](mtp-action-center.md)
