---
title: Microsoft 365 の情報バリア
description: Microsoft 365 で情報バリアを構成する方法について説明します。
keywords: Microsoft 365、インサイダー リスク、コンプライアンス
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
- m365solution-scenario
ms.openlocfilehash: a4c7b711c0a977e0980cd0c72f9369833e9e5c65
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423598"
---
# <a name="information-barriers-in-microsoft-365"></a><span data-ttu-id="69d26-104">Microsoft 365 の情報バリア</span><span class="sxs-lookup"><span data-stu-id="69d26-104">Information barriers in Microsoft 365</span></span>

<span data-ttu-id="69d26-105">Microsoft 365 は、グループや組織間のコミュニケーションとコラボレーションを可能にし、必要に応じて特定のユーザー グループ間の通信とコラボレーションを制限する方法をサポートします。</span><span class="sxs-lookup"><span data-stu-id="69d26-105">Microsoft 365 enables communication and collaboration across groups and organizations and supports ways to restrict communication and collaboration among specific groups of users when necessary.</span></span> <span data-ttu-id="69d26-106">これには、組織内で利益相反が発生しないように、2 つのグループ間の通信とコラボレーションを制限する状況やシナリオが含まれる場合があります。</span><span class="sxs-lookup"><span data-stu-id="69d26-106">This may include situations or scenarios where you want to restrict communication and collaboration between two groups to avoid a conflict of interest from occurring in your organization.</span></span> <span data-ttu-id="69d26-107">また、内部情報を保護するために組織内の特定のユーザー間の通信と共同作業を制限する必要がある場合も含まれます。</span><span class="sxs-lookup"><span data-stu-id="69d26-107">This may also include situations when you need to restrict communication and collaboration between certain people inside your organization to safeguard internal information.</span></span>

<span data-ttu-id="69d26-108">情報バリアは、Microsoft Teams、SharePoint Online、OneDrive for Business でサポートされています。</span><span class="sxs-lookup"><span data-stu-id="69d26-108">Information barriers are supported in Microsoft Teams, SharePoint Online, and OneDrive for Business.</span></span> <span data-ttu-id="69d26-109">コンプライアンス管理者または情報バリア管理者は、Microsoft Teams のユーザー グループ間の通信を許可または防止するポリシーを定義できます。</span><span class="sxs-lookup"><span data-stu-id="69d26-109">A compliance administrator or information barriers administrator can define policies to allow or prevent communications between groups of users in Microsoft Teams.</span></span> <span data-ttu-id="69d26-110">情報バリア ポリシーは、次のような状況で使用できます。</span><span class="sxs-lookup"><span data-stu-id="69d26-110">Information barrier policies can be used for situations like these:</span></span>

- <span data-ttu-id="69d26-111">当日のトレーダー グループのユーザーは、マーケティング チームとファイルの通信や共有を行う必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d26-111">User in the day trader group should not communicate or share files with the marketing team</span></span>
- <span data-ttu-id="69d26-112">会社の機密情報に取り組む財務担当者は、組織内の特定のグループとファイルを通信したり共有したりしな</span><span class="sxs-lookup"><span data-stu-id="69d26-112">Finance personnel working on confidential company information should not communicate or share files with certain groups within their organization</span></span>
- <span data-ttu-id="69d26-113">営業秘密資料を持つ内部チームは、組織内の特定のグループのユーザーとオンラインで通話したりチャットしたりしな</span><span class="sxs-lookup"><span data-stu-id="69d26-113">An internal team with trade secret material should not call or chat online with people in certain groups within their organization</span></span>
- <span data-ttu-id="69d26-114">リサーチ チームは、製品開発チームとオンラインでのみ通話またはチャットする必要があります。</span><span class="sxs-lookup"><span data-stu-id="69d26-114">A research team should only call or chat online with a product development team</span></span>

## <a name="configure-information-barriers-for-microsoft-365"></a><span data-ttu-id="69d26-115">Microsoft 365 の情報バリアを構成する</span><span class="sxs-lookup"><span data-stu-id="69d26-115">Configure information barriers for Microsoft 365</span></span>

<span data-ttu-id="69d26-116">組織の情報バリアを構成するには、次の手順を使用します。</span><span class="sxs-lookup"><span data-stu-id="69d26-116">Use the following steps to configure information barriers for your organization:</span></span>

![Insider リスク ソリューション情報の障壁の手順](../media/ir-solution-ib-steps.png)

1. <span data-ttu-id="69d26-118">Microsoft 365 の [情報バリアの](information-barriers.md) 詳細</span><span class="sxs-lookup"><span data-stu-id="69d26-118">Learn about [information barriers](information-barriers.md) in Microsoft 365</span></span>
2. <span data-ttu-id="69d26-119">前提条件 [とアクセス許可を構成する](information-barriers-policies.md#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="69d26-119">Configure [prerequisites and permissions](information-barriers-policies.md#prerequisites)</span></span>
3. <span data-ttu-id="69d26-120">組織内 [のユーザーをセグメント化する](information-barriers-policies.md#part-1-segment-users)</span><span class="sxs-lookup"><span data-stu-id="69d26-120">Segment [users in your organization](information-barriers-policies.md#part-1-segment-users)</span></span>
4. <span data-ttu-id="69d26-121">情報バリア ポリシー [の作成と構成](information-barriers-policies.md#part-2-define-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="69d26-121">Create and configure [information barrier policies](information-barriers-policies.md#part-2-define-information-barrier-policies)</span></span>
5. <span data-ttu-id="69d26-122">情報 [バリア ポリシーの適用](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span><span class="sxs-lookup"><span data-stu-id="69d26-122">Apply [information barrier policies](information-barriers-policies.md#part-3-apply-information-barrier-policies)</span></span>

## <a name="more-information-about-information-barriers"></a><span data-ttu-id="69d26-123">情報バリアの詳細</span><span class="sxs-lookup"><span data-stu-id="69d26-123">More information about information barriers</span></span>

- [<span data-ttu-id="69d26-124">情報障壁ポリシーの属性</span><span class="sxs-lookup"><span data-stu-id="69d26-124">Attributes for information barrier policies</span></span>](information-barriers-attributes.md)
- [<span data-ttu-id="69d26-125">情報バリア ポリシーの編集または削除</span><span class="sxs-lookup"><span data-stu-id="69d26-125">Edit or remove information barrier policies</span></span>](information-barriers-edit-segments-policies.md)