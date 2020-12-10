---
title: Microsoft 365 の情報障壁
description: Microsoft 365 で情報障壁を構成する方法について説明します。
keywords: Microsoft 365、内部者のリスク、コンプライアンス
localization_priority: Normal
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection:
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.openlocfilehash: 74a5b557ae610f8d008ad9d43bd2ccac43179131
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/09/2020
ms.locfileid: "49613845"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="bca9d-104">Microsoft 365 の情報障壁</span><span class="sxs-lookup"><span data-stu-id="bca9d-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="bca9d-105">Microsoft 365 は、グループと組織間での通信とコラボレーションを可能にし、必要に応じて特定のユーザーグループ間の通信とコラボレーションを制限する方法をサポートします。</span><span class="sxs-lookup"><span data-stu-id="bca9d-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="bca9d-106">これには、組織での競合を回避するために2つのグループ間の通信とコラボレーションを制限する必要がある状況やシナリオが含まれます。</span><span class="sxs-lookup"><span data-stu-id="bca9d-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="bca9d-107">これには、内部情報を保護するために組織内の特定のユーザー間での通信とコラボレーションを制限する必要がある場合もあります。</span><span class="sxs-lookup"><span data-stu-id="bca9d-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="bca9d-108">情報バリアは、Microsoft Teams、SharePoint Online、OneDrive for business でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="bca9d-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="bca9d-109">コンプライアンス管理者または情報障壁管理者は、Microsoft Teams のユーザーグループ間の通信を許可または禁止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="bca9d-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="bca9d-110">情報バリアポリシーは、次のような状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="bca9d-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="bca9d-111">営業担当営業グループのユーザーは、マーケティングチームとファイルを通信または共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="bca9d-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="bca9d-112">機密企業情報を扱う財務担当者は、組織内の特定のグループとファイルを通信または共有することはできません。</span><span class="sxs-lookup"><span data-stu-id="bca9d-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="bca9d-113">組織内の特定のグループに属するユーザーとの通信を、取引先機密資料を含む内部チームに対して行うことはできません。</span><span class="sxs-lookup"><span data-stu-id="bca9d-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="bca9d-114">研究チームは、製品開発チームとの通話またはオンラインチャットのみを行います。</span><span class="sxs-lookup"><span data-stu-id="bca9d-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="bca9d-115">Microsoft 365 の情報障壁を構成する</span><span class="sxs-lookup"><span data-stu-id="bca9d-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="bca9d-116">組織の情報障壁を構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="bca9d-116">Use the following steps to configure information barriers for your organization:</span></span>

![Insider リスクソリューション情報障壁の手順](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="bca9d-118">Microsoft 365 の [情報障壁](information-barriers.md) について</span><span class="sxs-lookup"><span data-stu-id="bca9d-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="bca9d-119">[前提条件とアクセス許可を](information-barriers-policies.md#prerequisites)構成する</span><span class="sxs-lookup"><span data-stu-id="bca9d-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="bca9d-120">[組織内のユーザーの](information-barriers-policies.md#part-1-segment-users)セグメント化</span><span class="sxs-lookup"><span data-stu-id="bca9d-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="bca9d-121">[情報バリアポリシー](information-barriers-policies.md#part-2-define-information-barrier-policies)を作成および構成する</span><span class="sxs-lookup"><span data-stu-id="bca9d-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="bca9d-122">[情報バリアポリシー](information-barriers-policies.md#part-3-apply-information-barrier-policies)の適用</span><span class="sxs-lookup"><span data-stu-id="bca9d-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="bca9d-123">情報障壁に関する詳細情報</span><span class="sxs-lookup"><span data-stu-id="bca9d-123">More information about information barriers</span></span>

- [<span data-ttu-id="bca9d-124">情報障壁ポリシーの属性</span><span class="sxs-lookup"><span data-stu-id="bca9d-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="bca9d-125">情報バリアポリシーを編集または削除する</span><span class="sxs-lookup"><span data-stu-id="bca9d-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)