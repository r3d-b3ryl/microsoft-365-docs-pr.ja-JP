---
title: Microsoft Teams
description: Teams がデバイスにインストールされ、その後更新される方法
keywords: Microsoft Managed Desktop, Microsoft 365, Service, documentation, apps, line-of-business apps, LOB apps
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920658"
---
# <a name="microsoft-teams"></a><span data-ttu-id="1a82d-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1a82d-104">Microsoft Teams</span></span>

<span data-ttu-id="1a82d-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) は組織 [のメッセージング](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) アプリであり、リアルタイムのコラボレーションとコミュニケーション、会議、ファイルとアプリの共有のためのワークスペースも提供します。</span><span class="sxs-lookup"><span data-stu-id="1a82d-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="1a82d-106">初期展開</span><span class="sxs-lookup"><span data-stu-id="1a82d-106">Initial deployment</span></span>

<span data-ttu-id="1a82d-107">ほとんどのハードウェア ベンダーは、イメージの一部として Teams をまだ含めないので、Microsoft Managed Desktop は Microsoft Intune を使用して Teams をデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="1a82d-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="1a82d-108">すべての管理対象デバイスには Teams .msi [パッケージ](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) がインストールされ、デバイスにサインインしているすべてのユーザーが Microsoft Teams を使用できる状態にできます。</span><span class="sxs-lookup"><span data-stu-id="1a82d-108">All managed devices have the [Teams .msi package](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="1a82d-109">パッケージのインストールが最初に完了すると、Teams は自動的に起動し、デスクトップにショートカットを追加します。</span><span class="sxs-lookup"><span data-stu-id="1a82d-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="1a82d-110">Microsoft Intune の変更点</span><span class="sxs-lookup"><span data-stu-id="1a82d-110">Microsoft Intune changes</span></span>

<span data-ttu-id="1a82d-111">Microsoft Managed Desktop は、Microsoft Teams の Azure ADに 2 つのアプリケーションを追加します。</span><span class="sxs-lookup"><span data-stu-id="1a82d-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="1a82d-112">デバイスに応じて、64 ビットまたは 32 ビットのクライアントに展開されます。</span><span class="sxs-lookup"><span data-stu-id="1a82d-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="1a82d-113">モダン ワークプレース – Teams Machine Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="1a82d-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="1a82d-114">モダン ワークプレース – Teams Machine Wide Installer x32</span><span class="sxs-lookup"><span data-stu-id="1a82d-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="1a82d-115">更新プログラム</span><span class="sxs-lookup"><span data-stu-id="1a82d-115">Updates</span></span>

<span data-ttu-id="1a82d-116">Teams は、Microsoft 365 Apps for enterprise とは別の更新パスに従い、デスクトップ クライアントは自動的に更新します。</span><span class="sxs-lookup"><span data-stu-id="1a82d-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="1a82d-117">Teams は数時間ごとに更新プログラムをチェックし、ダウンロードし、コンピューターがアイドル状態になるのを待って、更新プログラムをサイレント インストールします。</span><span class="sxs-lookup"><span data-stu-id="1a82d-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="1a82d-118">Teams 製品グループでは、管理者が更新プログラムを制御できないので、Microsoft Managed Desktop は標準の自動更新チャネル [を使用します](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。</span><span class="sxs-lookup"><span data-stu-id="1a82d-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="1a82d-119">Teams を手動で更新する</span><span class="sxs-lookup"><span data-stu-id="1a82d-119">Manually updating Teams</span></span>

<span data-ttu-id="1a82d-120">個々のユーザーは、アプリの右上部にある [プロファイル] ドロップダウン メニューで [更新プログラムの確認] を選択して更新    \*\*\*\*   プログラムをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="1a82d-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="1a82d-121">更新プログラムが利用可能な場合は、コンピューターがアイドル状態のときにダウンロードされ、サイレント インストールされます。</span><span class="sxs-lookup"><span data-stu-id="1a82d-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="1a82d-122">更新プログラムの配信の最適化</span><span class="sxs-lookup"><span data-stu-id="1a82d-122">Delivery optimization of updates</span></span>

<span data-ttu-id="1a82d-123">Teams 更新プログラムの配信の最適化は既定で有効になっています。管理者またはユーザーからのアクションは必要とされません。</span><span class="sxs-lookup"><span data-stu-id="1a82d-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span>