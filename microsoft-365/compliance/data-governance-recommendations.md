---
title: データ ガバナンスの推奨事項のためのコンテンツの識別方法
f1.keywords:
- NOCSH
ms.author: brendonb
author: cabailey
manager: laurawi
ms.date: 1/15/2019
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
ms.collection:
- SPO_Content
localization_priority: Priority
search.appverid:
- MOE150
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft 365 セキュリティ センターと Microsoft 365 コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士/依頼人特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。
ms.openlocfilehash: 9a022369fb783a498971c91664fa6532472d8589
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922611"
---
# <a name="how-content-is-identified-for-data-governance-recommendations"></a><span data-ttu-id="f2919-106">データ ガバナンスの推奨事項のためのコンテンツの識別方法</span><span class="sxs-lookup"><span data-stu-id="f2919-106">How content is identified for data-governance recommendations</span></span>

<span data-ttu-id="f2919-p102">Microsoft 365 セキュリティ センターと Microsoft 365 コンプライアンス センターは、組織の現在の設定に基づきデータ ガバナンスのための推奨事項を提供し、ユーザーによる設定作業を簡略化します。これらの推奨事項の一部は組織で特定のコンテンツを検出し、そのコンテンツを管理するための推奨手順を提供します。たとえば、重要な業務コンテンツ (弁護士/依頼人特権や秘密保持契約書に関わる情報など) を含むアイテムが推奨事項によって検出された際に、ユーザーは保持ラベルを自動適用し、必要に応じてアイテムを機密扱いにして保持することができます。</span><span class="sxs-lookup"><span data-stu-id="f2919-p102">The Microsoft 365 security center and Microsoft 365 compliance center provide recommendations for data governance based on your org's current setup and lets you set things up in a couple clicks. Some of these recommendations detect specific content in your organization and then provide recommended steps for managing that content. For example, a recommendation might detect items that contain business-critical content (such as attorney-client privilege or NDA info), and then let you automatically apply a retention label to those items to ensure that they're classified and retained as needed.</span></span>

<span data-ttu-id="f2919-110">このトピックでは、ユーザーに表示される可能性があるデータ ガバナンスの推奨事項を一覧表示し、それぞれの推奨事項をトリガーするコンテンツについて説明します。</span><span class="sxs-lookup"><span data-stu-id="f2919-110">This topic lists the data-governance recommendations you might see and describes what content is detected to trigger each one.</span></span>

## <a name="clean-up-voicemail"></a><span data-ttu-id="f2919-111">ボイスメールのクリーンアップ</span><span class="sxs-lookup"><span data-stu-id="f2919-111">Clean up voicemail</span></span>

<span data-ttu-id="f2919-p103">この推奨事項は、メッセージの種類が "ボイスメール" と識別されるメール メッセージがユーザーのメールボックスで検出されたときに表示されます。詳細については、「[Exchange でのメッセージのプロパティ](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="f2919-p103">This recommendation appears when email messages identified as the message type 'voicemail' are detected in users' mailboxes. Learn more about [message properties in Exchange](/exchange/policy-and-compliance/ediscovery/message-properties-and-search-operators?view=exchserver-2019#searchable-properties-in-exchange).</span></span>

## <a name="label-attorney-client-privilege-content"></a><span data-ttu-id="f2919-114">弁護士/依頼人特権関連コンテンツのラベル付け</span><span class="sxs-lookup"><span data-stu-id="f2919-114">Label attorney-client privilege content</span></span> 

<span data-ttu-id="f2919-115">この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2919-115">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="f2919-116">メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="f2919-116">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="f2919-117">ACP</span><span class="sxs-lookup"><span data-stu-id="f2919-117">ACP</span></span>
    - <span data-ttu-id="f2919-118">弁護士依頼人特権</span><span class="sxs-lookup"><span data-stu-id="f2919-118">Attorney Client Privilege</span></span>
    - <span data-ttu-id="f2919-119">弁護士/依頼人特権</span><span class="sxs-lookup"><span data-stu-id="f2919-119">Attorney-Client Privilege</span></span>
    - <span data-ttu-id="f2919-120">弁護士/依頼人特権がある</span><span class="sxs-lookup"><span data-stu-id="f2919-120">Attorney-Client Privileged</span></span>

- <span data-ttu-id="f2919-121">SharePoint ファイルまたは OneDrive ファイルで、これらのキーワードのいずれの組み合わせも検出されます</span><span class="sxs-lookup"><span data-stu-id="f2919-121">Any combination of these keywords are detected in SharePoint or OneDrive files:</span></span>
    - <span data-ttu-id="f2919-122">ACP</span><span class="sxs-lookup"><span data-stu-id="f2919-122">ACP</span></span>
    - <span data-ttu-id="f2919-123">弁護士依頼人特権\*</span><span class="sxs-lookup"><span data-stu-id="f2919-123">Attorney Client Privilege\*</span></span>
    - <span data-ttu-id="f2919-124">AC 特権</span><span class="sxs-lookup"><span data-stu-id="f2919-124">AC Privilege</span></span>

## <a name="retain-audio-files"></a><span data-ttu-id="f2919-125">オーディオ ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="f2919-125">Retain audio files</span></span>

<span data-ttu-id="f2919-126">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2919-126">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="f2919-127">.MP3</span><span class="sxs-lookup"><span data-stu-id="f2919-127">.MP3</span></span>
- <span data-ttu-id="f2919-128">.WMA</span><span class="sxs-lookup"><span data-stu-id="f2919-128">.WMA</span></span>
- <span data-ttu-id="f2919-129">.WAV</span><span class="sxs-lookup"><span data-stu-id="f2919-129">.WAV</span></span>
- <span data-ttu-id="f2919-130">.RA</span><span class="sxs-lookup"><span data-stu-id="f2919-130">.RA</span></span>
- <span data-ttu-id="f2919-131">.RAM</span><span class="sxs-lookup"><span data-stu-id="f2919-131">.RAM</span></span>
- <span data-ttu-id="f2919-132">.RM</span><span class="sxs-lookup"><span data-stu-id="f2919-132">.RM</span></span>
- <span data-ttu-id="f2919-133">.MID</span><span class="sxs-lookup"><span data-stu-id="f2919-133">.MID</span></span>
- <span data-ttu-id="f2919-134">.OGG</span><span class="sxs-lookup"><span data-stu-id="f2919-134">.OGG</span></span>
- <span data-ttu-id="f2919-135">.AIFF</span><span class="sxs-lookup"><span data-stu-id="f2919-135">.AIFF</span></span>
- <span data-ttu-id="f2919-136">.PCM</span><span class="sxs-lookup"><span data-stu-id="f2919-136">.PCM</span></span>
- <span data-ttu-id="f2919-137">.AAC</span><span class="sxs-lookup"><span data-stu-id="f2919-137">.AAC</span></span>
- <span data-ttu-id="f2919-138">.FLAC</span><span class="sxs-lookup"><span data-stu-id="f2919-138">.FLAC</span></span>
- <span data-ttu-id="f2919-139">.ALAC</span><span class="sxs-lookup"><span data-stu-id="f2919-139">.ALAC</span></span>

## <a name="retain-cad-files"></a><span data-ttu-id="f2919-140">CAD ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="f2919-140">Retain CAD files</span></span>

<span data-ttu-id="f2919-141">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2919-141">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="f2919-142">.3DXML</span><span class="sxs-lookup"><span data-stu-id="f2919-142">.3DXML</span></span>
- <span data-ttu-id="f2919-143">.ACIS</span><span class="sxs-lookup"><span data-stu-id="f2919-143">.ACIS</span></span>
- <span data-ttu-id="f2919-144">.ARC</span><span class="sxs-lookup"><span data-stu-id="f2919-144">.ARC</span></span>
- <span data-ttu-id="f2919-145">.ASM</span><span class="sxs-lookup"><span data-stu-id="f2919-145">.ASM</span></span>
- <span data-ttu-id="f2919-146">.CAT\*</span><span class="sxs-lookup"><span data-stu-id="f2919-146">.CAT\*</span></span>
- <span data-ttu-id="f2919-147">.CGR</span><span class="sxs-lookup"><span data-stu-id="f2919-147">.CGR</span></span>
- <span data-ttu-id="f2919-148">.DW\*</span><span class="sxs-lookup"><span data-stu-id="f2919-148">.DW\*</span></span>
- <span data-ttu-id="f2919-149">.DX\*</span><span class="sxs-lookup"><span data-stu-id="f2919-149">.DX\*</span></span>
- <span data-ttu-id="f2919-150">.EDRW</span><span class="sxs-lookup"><span data-stu-id="f2919-150">.EDRW</span></span>
- <span data-ttu-id="f2919-151">.IAM</span><span class="sxs-lookup"><span data-stu-id="f2919-151">.IAM</span></span>
- <span data-ttu-id="f2919-152">.IGES</span><span class="sxs-lookup"><span data-stu-id="f2919-152">.IGES</span></span>
- <span data-ttu-id="f2919-153">.IGS</span><span class="sxs-lookup"><span data-stu-id="f2919-153">.IGS</span></span>
- <span data-ttu-id="f2919-154">.IPT</span><span class="sxs-lookup"><span data-stu-id="f2919-154">.IPT</span></span>
- <span data-ttu-id="f2919-155">.JT</span><span class="sxs-lookup"><span data-stu-id="f2919-155">.JT</span></span>
- <span data-ttu-id="f2919-156">.MF1</span><span class="sxs-lookup"><span data-stu-id="f2919-156">.MF1</span></span>
- <span data-ttu-id="f2919-157">.NEU</span><span class="sxs-lookup"><span data-stu-id="f2919-157">.NEU</span></span>
- <span data-ttu-id="f2919-158">.PAR</span><span class="sxs-lookup"><span data-stu-id="f2919-158">.PAR</span></span>
- <span data-ttu-id="f2919-159">.PKG</span><span class="sxs-lookup"><span data-stu-id="f2919-159">.PKG</span></span>
- <span data-ttu-id="f2919-160">.PRC</span><span class="sxs-lookup"><span data-stu-id="f2919-160">.PRC</span></span>
- <span data-ttu-id="f2919-161">.PRT</span><span class="sxs-lookup"><span data-stu-id="f2919-161">.PRT</span></span>
- <span data-ttu-id="f2919-162">.PSM</span><span class="sxs-lookup"><span data-stu-id="f2919-162">.PSM</span></span>
- <span data-ttu-id="f2919-163">.PWD</span><span class="sxs-lookup"><span data-stu-id="f2919-163">.PWD</span></span>
- <span data-ttu-id="f2919-164">.SLD\*</span><span class="sxs-lookup"><span data-stu-id="f2919-164">.SLD\*</span></span>
- <span data-ttu-id="f2919-165">.STEP</span><span class="sxs-lookup"><span data-stu-id="f2919-165">.STEP</span></span>
- <span data-ttu-id="f2919-166">.STL</span><span class="sxs-lookup"><span data-stu-id="f2919-166">.STL</span></span>
- <span data-ttu-id="f2919-167">.STP</span><span class="sxs-lookup"><span data-stu-id="f2919-167">.STP</span></span>
- <span data-ttu-id="f2919-168">.U3D</span><span class="sxs-lookup"><span data-stu-id="f2919-168">.U3D</span></span>
- <span data-ttu-id="f2919-169">.UNV</span><span class="sxs-lookup"><span data-stu-id="f2919-169">.UNV</span></span>
- <span data-ttu-id="f2919-170">.VRML</span><span class="sxs-lookup"><span data-stu-id="f2919-170">.VRML</span></span>
- <span data-ttu-id="f2919-171">.WRL</span><span class="sxs-lookup"><span data-stu-id="f2919-171">.WRL</span></span>
- <span data-ttu-id="f2919-172">.X_\*</span><span class="sxs-lookup"><span data-stu-id="f2919-172">.X_\*</span></span>
- <span data-ttu-id="f2919-173">.XAS</span><span class="sxs-lookup"><span data-stu-id="f2919-173">.XAS</span></span>
- <span data-ttu-id="f2919-174">.XMT\*</span><span class="sxs-lookup"><span data-stu-id="f2919-174">.XMT\*</span></span>
- <span data-ttu-id="f2919-175">.XPR</span><span class="sxs-lookup"><span data-stu-id="f2919-175">.XPR</span></span>

## <a name="retain-image-files"></a><span data-ttu-id="f2919-176">画像ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="f2919-176">Retain image files</span></span>

<span data-ttu-id="f2919-177">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2919-177">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="f2919-178">.JPEG</span><span class="sxs-lookup"><span data-stu-id="f2919-178">.JPEG</span></span>
- <span data-ttu-id="f2919-179">.GIF</span><span class="sxs-lookup"><span data-stu-id="f2919-179">.GIF</span></span>
- <span data-ttu-id="f2919-180">.TIF\*</span><span class="sxs-lookup"><span data-stu-id="f2919-180">.TIF\*</span></span>
- <span data-ttu-id="f2919-181">.BMP</span><span class="sxs-lookup"><span data-stu-id="f2919-181">.BMP</span></span>
- <span data-ttu-id="f2919-182">.PNG</span><span class="sxs-lookup"><span data-stu-id="f2919-182">.PNG</span></span>
- <span data-ttu-id="f2919-183">.RAW</span><span class="sxs-lookup"><span data-stu-id="f2919-183">.RAW</span></span>
- <span data-ttu-id="f2919-184">.PSD</span><span class="sxs-lookup"><span data-stu-id="f2919-184">.PSD</span></span>
- <span data-ttu-id="f2919-185">.PSP</span><span class="sxs-lookup"><span data-stu-id="f2919-185">.PSP</span></span>
- <span data-ttu-id="f2919-186">.JPG</span><span class="sxs-lookup"><span data-stu-id="f2919-186">.JPG</span></span>
- <span data-ttu-id="f2919-187">.EXIF</span><span class="sxs-lookup"><span data-stu-id="f2919-187">.EXIF</span></span>
- <span data-ttu-id="f2919-188">.PPM</span><span class="sxs-lookup"><span data-stu-id="f2919-188">.PPM</span></span>
- <span data-ttu-id="f2919-189">.PGM</span><span class="sxs-lookup"><span data-stu-id="f2919-189">.PGM</span></span>
- <span data-ttu-id="f2919-190">.PBM</span><span class="sxs-lookup"><span data-stu-id="f2919-190">.PBM</span></span>
- <span data-ttu-id="f2919-191">.PNM</span><span class="sxs-lookup"><span data-stu-id="f2919-191">.PNM</span></span>
- <span data-ttu-id="f2919-192">.WEBP</span><span class="sxs-lookup"><span data-stu-id="f2919-192">.WEBP</span></span>

## <a name="retain-nda-content"></a><span data-ttu-id="f2919-193">NDA 関連コンテンツの保持</span><span class="sxs-lookup"><span data-stu-id="f2919-193">Retain NDA content</span></span> 

<span data-ttu-id="f2919-194">この推奨事項は、次のいずれかの条件が満たされた場合に表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2919-194">This recommendation appears when either of the following criteria are met.</span></span>

- <span data-ttu-id="f2919-195">メール メッセージの本文で、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="f2919-195">Any of combination of these keywords is detected in the body of an email message:</span></span>
    - <span data-ttu-id="f2919-196">NDA</span><span class="sxs-lookup"><span data-stu-id="f2919-196">NDA</span></span>
    - <span data-ttu-id="f2919-197">"秘密保持契約"</span><span class="sxs-lookup"><span data-stu-id="f2919-197">"Non-Disclosure Agreement"</span></span>
    - <span data-ttu-id="f2919-198">"秘密保持契約"</span><span class="sxs-lookup"><span data-stu-id="f2919-198">"Non Disclosure Agreement"</span></span>

- <span data-ttu-id="f2919-199">SharePoint または OneDrive の .PDF または .DOC ファイルで、これらのキーワードのいずれの組み合わせも検出されます。</span><span class="sxs-lookup"><span data-stu-id="f2919-199">Any combination of these keywords are detected in .PDF or .DOC files in SharePoint or OneDrive:</span></span>
    - <span data-ttu-id="f2919-200">NDA</span><span class="sxs-lookup"><span data-stu-id="f2919-200">NDA</span></span>
    - <span data-ttu-id="f2919-201">“秘密保持契約”</span><span class="sxs-lookup"><span data-stu-id="f2919-201">Non Disclosure Agreement</span></span>

## <a name="retain-software-development-files"></a><span data-ttu-id="f2919-202">ソフトウェア開発ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="f2919-202">Retain software development files</span></span>

<span data-ttu-id="f2919-203">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2919-203">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="f2919-204">.ASAX</span><span class="sxs-lookup"><span data-stu-id="f2919-204">.ASAX</span></span>
- <span data-ttu-id="f2919-205">.ASM</span><span class="sxs-lookup"><span data-stu-id="f2919-205">.ASM</span></span>
- <span data-ttu-id="f2919-206">.ASP\*</span><span class="sxs-lookup"><span data-stu-id="f2919-206">.ASP\*</span></span>
- <span data-ttu-id="f2919-207">.BAT</span><span class="sxs-lookup"><span data-stu-id="f2919-207">.BAT</span></span>
- <span data-ttu-id="f2919-208">.CONFIG</span><span class="sxs-lookup"><span data-stu-id="f2919-208">.CONFIG</span></span>
- <span data-ttu-id="f2919-209">.CS</span><span class="sxs-lookup"><span data-stu-id="f2919-209">.CS</span></span>
- <span data-ttu-id="f2919-210">.CSS</span><span class="sxs-lookup"><span data-stu-id="f2919-210">.CSS</span></span>
- <span data-ttu-id="f2919-211">.DISCO</span><span class="sxs-lookup"><span data-stu-id="f2919-211">.DISCO</span></span>
- <span data-ttu-id="f2919-212">.HTM\*</span><span class="sxs-lookup"><span data-stu-id="f2919-212">.HTM\*</span></span>
- <span data-ttu-id="f2919-213">.INC</span><span class="sxs-lookup"><span data-stu-id="f2919-213">.INC</span></span>
- <span data-ttu-id="f2919-214">.JAD</span><span class="sxs-lookup"><span data-stu-id="f2919-214">.JAD</span></span>
- <span data-ttu-id="f2919-215">.JAVA</span><span class="sxs-lookup"><span data-stu-id="f2919-215">.JAVA</span></span>
- <span data-ttu-id="f2919-216">.JS\*</span><span class="sxs-lookup"><span data-stu-id="f2919-216">.JS\*</span></span>
- <span data-ttu-id="f2919-217">.LIB</span><span class="sxs-lookup"><span data-stu-id="f2919-217">.LIB</span></span>
- <span data-ttu-id="f2919-218">.O</span><span class="sxs-lookup"><span data-stu-id="f2919-218">.O</span></span>
- <span data-ttu-id="f2919-219">.PHP</span><span class="sxs-lookup"><span data-stu-id="f2919-219">.PHP</span></span>
- <span data-ttu-id="f2919-220">.RC</span><span class="sxs-lookup"><span data-stu-id="f2919-220">.RC</span></span>
- <span data-ttu-id="f2919-221">.RESX</span><span class="sxs-lookup"><span data-stu-id="f2919-221">.RESX</span></span>
- <span data-ttu-id="f2919-222">.RPT</span><span class="sxs-lookup"><span data-stu-id="f2919-222">.RPT</span></span>
- <span data-ttu-id="f2919-223">.RSS</span><span class="sxs-lookup"><span data-stu-id="f2919-223">.RSS</span></span>
- <span data-ttu-id="f2919-224">.SCPT</span><span class="sxs-lookup"><span data-stu-id="f2919-224">.SCPT</span></span>
- <span data-ttu-id="f2919-225">.SRC</span><span class="sxs-lookup"><span data-stu-id="f2919-225">.SRC</span></span>
- <span data-ttu-id="f2919-226">.VB\*</span><span class="sxs-lookup"><span data-stu-id="f2919-226">.VB\*</span></span>
- <span data-ttu-id="f2919-227">.WSF</span><span class="sxs-lookup"><span data-stu-id="f2919-227">.WSF</span></span>
- <span data-ttu-id="f2919-228">.XCODEPROJ</span><span class="sxs-lookup"><span data-stu-id="f2919-228">.XCODEPROJ</span></span>
- <span data-ttu-id="f2919-229">.XML</span><span class="sxs-lookup"><span data-stu-id="f2919-229">.XML</span></span>
- <span data-ttu-id="f2919-230">.XSD</span><span class="sxs-lookup"><span data-stu-id="f2919-230">.XSD</span></span>
- <span data-ttu-id="f2919-231">.XSL\*</span><span class="sxs-lookup"><span data-stu-id="f2919-231">.XSL\*</span></span>

## <a name="retain-video-files"></a><span data-ttu-id="f2919-232">ビデオ ファイルの保持</span><span class="sxs-lookup"><span data-stu-id="f2919-232">Retain video files</span></span>

<span data-ttu-id="f2919-233">この推奨事項は、SharePoint または OneDrive で次のファイルの種類のいずれかが検出されたときに表示されます。</span><span class="sxs-lookup"><span data-stu-id="f2919-233">This recommendation appears when any of the following file types are detected in SharePoint or OneDrive.</span></span>

- <span data-ttu-id="f2919-234">.AVCHD</span><span class="sxs-lookup"><span data-stu-id="f2919-234">.AVCHD</span></span>
- <span data-ttu-id="f2919-235">.AVI</span><span class="sxs-lookup"><span data-stu-id="f2919-235">.AVI</span></span>
- <span data-ttu-id="f2919-236">.FLV</span><span class="sxs-lookup"><span data-stu-id="f2919-236">.FLV</span></span>
- <span data-ttu-id="f2919-237">.MOV</span><span class="sxs-lookup"><span data-stu-id="f2919-237">.MOV</span></span>
- <span data-ttu-id="f2919-238">.MP2V</span><span class="sxs-lookup"><span data-stu-id="f2919-238">.MP2V</span></span>
- <span data-ttu-id="f2919-239">.MP4</span><span class="sxs-lookup"><span data-stu-id="f2919-239">.MP4</span></span>
- <span data-ttu-id="f2919-240">.MP4V</span><span class="sxs-lookup"><span data-stu-id="f2919-240">.MP4V</span></span>
- <span data-ttu-id="f2919-241">.MPE</span><span class="sxs-lookup"><span data-stu-id="f2919-241">.MPE</span></span>
- <span data-ttu-id="f2919-242">.MPEG</span><span class="sxs-lookup"><span data-stu-id="f2919-242">.MPEG</span></span>
- <span data-ttu-id="f2919-243">.MPEG1</span><span class="sxs-lookup"><span data-stu-id="f2919-243">.MPEG1</span></span>
- <span data-ttu-id="f2919-244">.MPEG2</span><span class="sxs-lookup"><span data-stu-id="f2919-244">.MPEG2</span></span>
- <span data-ttu-id="f2919-245">.MPEG4</span><span class="sxs-lookup"><span data-stu-id="f2919-245">.MPEG4</span></span>
- <span data-ttu-id="f2919-246">.MPG</span><span class="sxs-lookup"><span data-stu-id="f2919-246">.MPG</span></span>
- <span data-ttu-id="f2919-247">.MPG2</span><span class="sxs-lookup"><span data-stu-id="f2919-247">.MPG2</span></span>
- <span data-ttu-id="f2919-248">.MPG4</span><span class="sxs-lookup"><span data-stu-id="f2919-248">.MPG4</span></span>
- <span data-ttu-id="f2919-249">.WMV</span><span class="sxs-lookup"><span data-stu-id="f2919-249">.WMV</span></span>
- <span data-ttu-id="f2919-250">.XMV</span><span class="sxs-lookup"><span data-stu-id="f2919-250">.XMV</span></span>