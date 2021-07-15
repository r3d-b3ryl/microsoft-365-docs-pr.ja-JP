---
title: アプリ ポリシーの詳細について説明します
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: アプリ ポリシーの詳細について説明します。
ms.openlocfilehash: 6d4ff23ca0e09f5e410d32d6ced144afc0c4bb15
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420362"
---
# <a name="learn-about-app-policies"></a><span data-ttu-id="79784-103">アプリ ポリシーの詳細について説明します</span><span class="sxs-lookup"><span data-stu-id="79784-103">Learn about app policies</span></span>

><span data-ttu-id="79784-104">*[セキュリティとコンプライアンスのための Microsoft 365 ライセンシング ガイダンス](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="79784-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="79784-105">Microsoft アプリ ガバナンスは、Microsoft 365 テナント内の逸脱したアプリの動作を検出し、表示、調査、解決できるアラートを生成します。</span><span class="sxs-lookup"><span data-stu-id="79784-105">Microsoft app governance detects anomalous app behavior in your Microsoft 365 tenant and generates alerts that you can see, investigate, and resolve.</span></span> <span data-ttu-id="79784-106">この装備された検出機能以外にも、一連の既定のテンプレートを使用して、その他のアラートを生成する独自のアプリ ポリシーを作成できます。</span><span class="sxs-lookup"><span data-stu-id="79784-106">Beyond this built-in detection capability, you can use a set of default templates to create your own app policies that generate other alerts.</span></span>

<span data-ttu-id="79784-107">これらの、アプリとユーザーについてのパターンと振る舞いに関するポリシーは、コンプライアンス違反または悪意のアプリを使用してしまうことからユーザーを守ることができ、そしてリスクのあるアプリがテナントのデータにアクセスすることを制限できます。</span><span class="sxs-lookup"><span data-stu-id="79784-107">These policies for app and user patterns and behaviors can protect your users from using non-compliant or malicious apps and limit the access of risky apps to your tenant data.</span></span>

<span data-ttu-id="79784-108">アプリのポリシー管理に必要な管理者ロールの簡潔なレビューがこちらにあります。</span><span class="sxs-lookup"><span data-stu-id="79784-108">Here's a quick review of required administrator roles for app policy management.</span></span>

| <span data-ttu-id="79784-109">役割</span><span class="sxs-lookup"><span data-stu-id="79784-109">Role</span></span> | <span data-ttu-id="79784-110">ポリシーを読み取る</span><span class="sxs-lookup"><span data-stu-id="79784-110">Read policies</span></span> | <span data-ttu-id="79784-111">ポリシーの作成、更新、または削除</span><span class="sxs-lookup"><span data-stu-id="79784-111">Create, update, or delete policies</span></span> |
|:-------|:-----|:-------|
| <span data-ttu-id="79784-112">コンプライアンス管理者</span><span class="sxs-lookup"><span data-stu-id="79784-112">Compliance Administrator</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |
| <span data-ttu-id="79784-115">コンプライアンス 閲覧者</span><span class="sxs-lookup"><span data-stu-id="79784-115">Compliance Reader</span></span> | ![チェック マーク](..\media\checkmark.png) |  |
| <span data-ttu-id="79784-117">グローバル管理者</span><span class="sxs-lookup"><span data-stu-id="79784-117">Global Administrator</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |
| <span data-ttu-id="79784-120">グローバル閲覧者</span><span class="sxs-lookup"><span data-stu-id="79784-120">Global Reader</span></span>  | ![チェック マーク](..\media\checkmark.png) |  |
| <span data-ttu-id="79784-122">セキュリティ管理者</span><span class="sxs-lookup"><span data-stu-id="79784-122">Security Administrator</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |
| <span data-ttu-id="79784-125">セキュリティ閲覧者</span><span class="sxs-lookup"><span data-stu-id="79784-125">Security Reader</span></span>  | ![チェック マーク](..\media\checkmark.png) |  |
| <span data-ttu-id="79784-127">セキュリティ オペレーター</span><span class="sxs-lookup"><span data-stu-id="79784-127">Security Operator</span></span> | ![チェック マーク](..\media\checkmark.png) | ![チェック マーク](..\media\checkmark.png) |
||||

<!--
How app policies are the method by which MAPG detects app anomolies resulting in detection (alerts) and remediation (manual or automatic) 


CFA #2 Scenario 1: As an admin, I can quickly set up policies to govern M365 apps in my tenant using MAPG out-of-the-box templates
CFA #2 Scenario 2: As an admin, I can create customized policies to govern M365 apps in my tenant to meet my organizations requirements.
CFA #2 Scenario 3: As an admin or policy reviewer, I can view all policies created in my environment and quickly see which policies have associated alerts. 
CFA #2 Scenario 4: As an admin, I can adjust policies efficiently to meet changing needs.

App policy templates

- Basic info
- Policy settings and conditions
- Actions
- Status

--> 

## <a name="next-step"></a><span data-ttu-id="79784-130">次の手順</span><span class="sxs-lookup"><span data-stu-id="79784-130">Next step</span></span>

[<span data-ttu-id="79784-131">アプリ ポリシーを用意して始めましょう。</span><span class="sxs-lookup"><span data-stu-id="79784-131">Get started with app policies.</span></span>](app-governance-app-policies-get-started.md)
