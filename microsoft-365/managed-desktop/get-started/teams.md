---
title: Microsoft Teams
description: Teams をデバイスにインストールし、後で更新する方法
keywords: Microsoft マネージドデスクトップ、Microsoft 365、サービス、ドキュメント、アプリ、基幹業務アプリ、LOB アプリ
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950941"
---
# <a name="microsoft-teams"></a><span data-ttu-id="b32fb-104">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b32fb-104">Microsoft Teams</span></span>

<span data-ttu-id="b32fb-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) は、組織の [メッセージングアプリ](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) であり、リアルタイムのコラボレーション、コミュニケーション、会議、およびファイルとアプリの共有のためのワークスペースも提供します。</span><span class="sxs-lookup"><span data-stu-id="b32fb-105">[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) is a [messaging app](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) for your organization that also provides a workspace for real-time collaboration and communication, meetings, and file and app sharing.</span></span>

## <a name="initial-deployment"></a><span data-ttu-id="b32fb-106">初期展開</span><span class="sxs-lookup"><span data-stu-id="b32fb-106">Initial deployment</span></span>

<span data-ttu-id="b32fb-107">ほとんどのハードウェアベンダーには、Teams が画像の一部として含まれていないため、Microsoft Managed Desktop は Microsoft Intune を使用してチームをデバイスに展開します。</span><span class="sxs-lookup"><span data-stu-id="b32fb-107">Most hardware vendors don't yet include Teams as a part of their images, so Microsoft Managed Desktop deploys Teams to your devices by using Microsoft Intune.</span></span> <span data-ttu-id="b32fb-108">すべての管理対象デバイスに [Teams .msi パッケージ](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) がインストールされており、デバイスにサインインするすべてのユーザーが Microsoft teams を使用する準備が整っていることを確認します。</span><span class="sxs-lookup"><span data-stu-id="b32fb-108">All managed devices have the [Teams .msi package](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) installed, ensuring that all users who sign in to a device have Microsoft Teams ready to use.</span></span> <span data-ttu-id="b32fb-109">最初にパッケージがインストールを終了すると、Teams が自動的に起動し、デスクトップへのショートカットが追加されます。</span><span class="sxs-lookup"><span data-stu-id="b32fb-109">When the package first finishes installing, Teams automatically starts and adds a shortcut to the desktop.</span></span>

### <a name="microsoft-intune-changes"></a><span data-ttu-id="b32fb-110">Microsoft Intune の変更</span><span class="sxs-lookup"><span data-stu-id="b32fb-110">Microsoft Intune changes</span></span>

<span data-ttu-id="b32fb-111">Microsoft マネージドデスクトップでは、Microsoft Teams 用の Azure AD 組織に2つのアプリケーションが追加されています。</span><span class="sxs-lookup"><span data-stu-id="b32fb-111">Microsoft Managed Desktop adds two applications to your Azure AD organization for Microsoft Teams.</span></span> <span data-ttu-id="b32fb-112">デバイスに応じて、次のように64ビットまたは32ビットのどちらかのクライアントに展開されます。</span><span class="sxs-lookup"><span data-stu-id="b32fb-112">They are deployed to either 64-bit or 32-bit clients as appropriate for the device:</span></span>  

- <span data-ttu-id="b32fb-113">モダンワークプレース: Teams Pc Wide Installer x64</span><span class="sxs-lookup"><span data-stu-id="b32fb-113">Modern Workplace – Teams Machine Wide Installer x64</span></span>  
- <span data-ttu-id="b32fb-114">モダンワークプレース-Teams コンピューター全体のインストーラー x32</span><span class="sxs-lookup"><span data-stu-id="b32fb-114">Modern Workplace – Teams Machine Wide Installer x32</span></span>

## <a name="updates"></a><span data-ttu-id="b32fb-115">更新プログラム</span><span class="sxs-lookup"><span data-stu-id="b32fb-115">Updates</span></span>

<span data-ttu-id="b32fb-116">Teams は、Microsoft 365 Apps for enterprise とデスクトップクライアントを自動的に更新する別の更新パスに従います。</span><span class="sxs-lookup"><span data-stu-id="b32fb-116">Teams follows a separate update path from Microsoft 365 Apps for enterprise and the desktop client updates itself automatically.</span></span> <span data-ttu-id="b32fb-117">Teams は数時間ごとに更新をチェックし、それらをダウンロードして、コンピューターがアイドル状態になってから更新プログラムをサイレントインストールするまで待機します。</span><span class="sxs-lookup"><span data-stu-id="b32fb-117">Teams checks for updates every few hours, downloads them, and then waits for the computer to be idle before silently installing the update.</span></span>  

<span data-ttu-id="b32fb-118">Teams 製品グループでは、管理者が更新プログラムを制御することを許可していないため、Microsoft Managed Desktop は [標準の自動更新チャネル](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)を使用します。</span><span class="sxs-lookup"><span data-stu-id="b32fb-118">The Teams product group doesn't allow admins to control updates, so Microsoft Managed Desktop uses the [standard automatic update channel](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).</span></span>

### <a name="manually-updating-teams"></a><span data-ttu-id="b32fb-119">Teams を手動で更新する</span><span class="sxs-lookup"><span data-stu-id="b32fb-119">Manually updating Teams</span></span>

<span data-ttu-id="b32fb-120">各ユーザーは**Check for updates**   、 **Profile**   アプリの右上にある [プロファイル] ドロップダウンメニューで [更新プログラムの確認] を選択して更新プログラムをダウンロードすることもできます。</span><span class="sxs-lookup"><span data-stu-id="b32fb-120">Individual users can also download updates by selecting **Check for updates** on the **Profile** drop-down menu at the top right of the app.</span></span> <span data-ttu-id="b32fb-121">更新プログラムが利用可能な場合は、コンピューターがアイドル状態になったときにダウンロードされ、サイレントにインストールされます。</span><span class="sxs-lookup"><span data-stu-id="b32fb-121">If an update is available, it will be downloaded and silently installed when the computer is idle.</span></span>

## <a name="delivery-optimization-of-updates"></a><span data-ttu-id="b32fb-122">更新プログラムの配信の最適化</span><span class="sxs-lookup"><span data-stu-id="b32fb-122">Delivery optimization of updates</span></span>

<span data-ttu-id="b32fb-123">Teams の更新の配信の最適化は既定で有効になっており、管理者またはユーザーからのアクションは必要ありません。</span><span class="sxs-lookup"><span data-stu-id="b32fb-123">Delivery optimization for Teams updates is turned on by default and requires no action from admins or users.</span></span> 