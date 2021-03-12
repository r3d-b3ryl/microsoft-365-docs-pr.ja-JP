---
title: メッセージ暗号化ビューアー アプリの非推奨
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 365 Office (OME) ビューアー アプリは、2018 年に Android ストアと Apple ストアから削除されました。
ms.openlocfilehash: bb96601a8a542d53f6732ab9316051c1a820ba46
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741524"
---
# <a name="deprecating-message-encryption-viewer-app"></a><span data-ttu-id="eb8d0-103">メッセージ暗号化ビューアー アプリの非推奨</span><span class="sxs-lookup"><span data-stu-id="eb8d0-103">Deprecating Message Encryption Viewer App</span></span>

<span data-ttu-id="eb8d0-104">2018 年 8 月 15 日、Android ストアと Apple ストアから Office 365 Message Encryption (OME) ビューアー モバイル アプリが削除されました。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-104">On August 15, 2018, we removed the Office 365 Message Encryption (OME) Viewer mobile app from Android and Apple stores.</span></span> <span data-ttu-id="eb8d0-105">Apple Office Android 携帯電話で以前のバージョンの OME で暗号化された電子メール メッセージと添付ファイルを読み取るには、365 Message Encryption Viewer モバイル アプリが必要でした。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-105">The Office 365 Message Encryption Viewer mobile app was required to read email messages and attachments that were encrypted with the previous version of OME on Apple and Android phones.</span></span> <span data-ttu-id="eb8d0-106">OME ビューアー アプリを削除する以外に、以前のバージョンの OME に他の変更を加える必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-106">Apart from removing the OME Viewer app, we are not making any other changes to the previous version of OME.</span></span>
  
## <a name="changes-from-august-2018"></a><span data-ttu-id="eb8d0-107">2018 年 8 月からの変更点</span><span class="sxs-lookup"><span data-stu-id="eb8d0-107">Changes from August 2018</span></span>

<span data-ttu-id="eb8d0-108">2017 年 9 月に発表された新しいバージョン [の Office 365 Message Encryption](https://aka.ms/ome2017) がリリースされ、ユーザーはモバイル アプリの要件を満たさずに組織の内部または外部の誰にでも暗号化および保護されたメッセージを送信できます。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-108">As announced September 2017, we have released a new version of [Office 365 Message Encryption](https://aka.ms/ome2017) so that users can send encrypted and protected messages to anyone inside or outside the organization without the requirement of the mobile app.</span></span> <span data-ttu-id="eb8d0-109">それ以来、次の機能が追加されました。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-109">Since then, we've added additional capabilities:</span></span>
  
- [<span data-ttu-id="eb8d0-110">暗号化専用テンプレート</span><span class="sxs-lookup"><span data-stu-id="eb8d0-110">Encrypt-only template</span></span>](https://aka.ms/encryptonly)

- [<span data-ttu-id="eb8d0-111">添付ファイルの復号化を制御する</span><span class="sxs-lookup"><span data-stu-id="eb8d0-111">Control to decrypt attachments</span></span>](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

<span data-ttu-id="eb8d0-112">この変更により、ユーザーは 8 月 1 日から Office 365 Message Encryption Viewer モバイル アプリをダウンロードできなくなりました。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-112">With this change, users will no longer be able to download the Office 365 Message Encryption Viewer mobile app beginning August 1.</span></span> <span data-ttu-id="eb8d0-113">その結果、一部の Android および Apple モバイル デバイスでは、メール受信者が以前のバージョンの OME で暗号化されたメッセージを読み取れない場合があります。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-113">As a result, mail recipients may not be able to read messages encrypted with the previous version of OME on some Android and Apple mobile devices.</span></span> <span data-ttu-id="eb8d0-114">ただし、これらのメッセージは、(デスクトップ ブラウザーを介して) 個人のコンピューターで読み取る可能性があります。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-114">However, they will still be able to read these messages on personal computers (via desktop browsers).</span></span> <span data-ttu-id="eb8d0-115">アプリを既にダウンロードしているユーザーは、引き続きアプリを使用できます。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-115">Users who have already downloaded the app will continue to be able to use it.</span></span>
  
## <a name="why-this-change-was-made"></a><span data-ttu-id="eb8d0-116">この変更が行われた理由</span><span class="sxs-lookup"><span data-stu-id="eb8d0-116">Why this change was made</span></span>

<span data-ttu-id="eb8d0-117">OME の新しいバージョンでは、保護された電子メール メッセージと添付ファイルを読み取るためにモバイル アプリが必要なくなりました。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-117">The new version of OME no longer requires a mobile app to read protected email messages and attachments.</span></span> <span data-ttu-id="eb8d0-118">新しい OME 機能を使用しているお客様は、Outlook モバイルで保護されたメッセージを表示し、非顧客はブラウザーで保護されたメッセージを表示できます。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-118">Customers using the new OME capabilities can view the protected message in Outlook mobile and non-customers can view protected messages in a browser.</span></span>
  
<span data-ttu-id="eb8d0-119">ユーザーにモバイル アプリのダウンロードを要求する場合は、保護されたメッセージを表示するためのもう 1 つのハードルです。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-119">Requiring users to download a mobile app is another hurdle for customers to view protected messages.</span></span> <span data-ttu-id="eb8d0-120">365 Officeの新しい機能により、モバイル エクスペリエンスが向上します。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-120">The new Office 365 Message Encryption capabilities provide a better mobile experience.</span></span>
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a><span data-ttu-id="eb8d0-121">365 Message Encryption の以前のバージョンOffice使用できる</span><span class="sxs-lookup"><span data-stu-id="eb8d0-121">Can I still use the previous version of Office 365 Message Encryption</span></span>

<span data-ttu-id="eb8d0-122">Office 365 Message Encryption の以前のバージョンは、現時点では廃止されませんが、新しいバージョンの Office 365 Message Encryption が大幅に強化され、機密データの暗号化と権限の保護が容易になり、ユーザーが Outlook (デスクトップ、モバイル) で保護されたメッセージを直接読み取る機能を含め、すべてのデバイスで機密データを簡単に保護できます。、および Web)。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-122">The previous version of Office 365 Message Encryption will not be deprecated at this time, however, we have made significant enhancements to the new version of Office 365 Message Encryption, which make it easier to encrypt and rights protect sensitive data to anyone and on any device - including the ability for users to read protected messages directly in Outlook (desktop, mobile, and web).</span></span> 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a><span data-ttu-id="eb8d0-123">この変更の準備に必要な操作</span><span class="sxs-lookup"><span data-stu-id="eb8d0-123">What do I need to do to prepare for this change</span></span>

<span data-ttu-id="eb8d0-124">組織が現在、OME ビューアー アプリを必要とする受信者に暗号化された添付ファイルを送信している場合は、ドキュメントとトレーニング リソースを更新する必要があります。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-124">If your organization currently sends encrypted attachments to recipients that require the OME Viewer app, you should update your documentation and training resources.</span></span>
  
<span data-ttu-id="eb8d0-125">組織が新しい機能と改善された機能を利用できるよう、既存の Exchange メール フロー ルールを更新して、現在のバージョンの OME を使用することをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-125">We recommend updating existing Exchange mail flow rules to use the current version of OME so that your organization can take advantage of the new and improved capabilities.</span></span> <span data-ttu-id="eb8d0-126">新しい OME 機能を設定すると、受信者はモバイル デバイスで暗号化されたメッセージを読み取る OME ビューアー アプリを必要としません。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-126">Once you have set up the new OME capabilities, recipients won't need the OME Viewer app to read encrypted messages on mobile devices.</span></span>
  
<span data-ttu-id="eb8d0-127">Microsoft では、組織に妥当な場合は、すぐに新しい OME 機能に移行する計画を立てをお勧めします。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-127">Microsoft recommends that you make a plan to move to the new OME capabilities as soon as it is reasonable for your organization.</span></span> <span data-ttu-id="eb8d0-128">手順については [、「Set up new Office 365 Message Encryption capabilitis」を参照してください](set-up-new-message-encryption-capabilities.md)。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-128">For instructions, see [Set up new Office 365 Message Encryption capabilities](set-up-new-message-encryption-capabilities.md).</span></span> <span data-ttu-id="eb8d0-129">新しい機能が最初に機能する方法の詳細については [、「365 Message Encryption](ome.md)」を参照Office参照してください。</span><span class="sxs-lookup"><span data-stu-id="eb8d0-129">If you want to find out more about how the new capabilities work first, see [Office 365 Message Encryption](ome.md).</span></span>
  

