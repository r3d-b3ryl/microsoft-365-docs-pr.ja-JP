---
title: Microsoft マネージド デスクトップ用に、印刷リソースを準備する
description: 印刷がスムーズに機能するための重要な手順
keywords: Microsoft マネージド デスクトップ、Microsoft 365、サービス、ドキュメント
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 3decc7d67decc5557e7921e68108e2ddb447f0fd
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924554"
---
# <a name="prepare-printing-resources-for-microsoft-managed-desktop"></a><span data-ttu-id="885d2-104">Microsoft マネージド デスクトップ用に、印刷リソースを準備する</span><span class="sxs-lookup"><span data-stu-id="885d2-104">Prepare printing resources for Microsoft Managed Desktop</span></span>

<span data-ttu-id="885d2-105">Microsoft Managed Desktop に登録する準備が整ったら、印刷要件を評価し、環境に適切なアプローチを決定する必要があります。</span><span class="sxs-lookup"><span data-stu-id="885d2-105">As you get ready to enroll in Microsoft Managed Desktop, you should evaluate your printing requirements and determine the right approach for your environment.</span></span> <span data-ttu-id="885d2-106">次の 3 つのオプションがあります。</span><span class="sxs-lookup"><span data-stu-id="885d2-106">You have three options:</span></span>
 
- <span data-ttu-id="885d2-107">Microsoft ユニバーサル 印刷ソリューションを展開して、Microsoft Managed Desktop デバイスがプリンターを簡単に検出できます。</span><span class="sxs-lookup"><span data-stu-id="885d2-107">Deploy the Microsoft Universal Print solution to make it easy for Microsoft Managed Desktop devices to discover printers.</span></span> <span data-ttu-id="885d2-108">詳細については [、「What is Universal Print 」を参照してください](/universal-print/fundamentals/universal-print-whatis)。</span><span class="sxs-lookup"><span data-stu-id="885d2-108">For more information, see [What is Universal Print](/universal-print/fundamentals/universal-print-whatis).</span></span>
- <span data-ttu-id="885d2-109">カスタム PowerShell スクリプトを使用してプリンターを直接展開します。</span><span class="sxs-lookup"><span data-stu-id="885d2-109">Deploy printers directly by using a custom PowerShell script.</span></span> <span data-ttu-id="885d2-110">「ローカル プリンターのセットアップ [」セクションの手順に従](#set-up-local-printers) います。</span><span class="sxs-lookup"><span data-stu-id="885d2-110">Follow the steps in the [Set up local printers](#set-up-local-printers) section.</span></span>
- <span data-ttu-id="885d2-111">Azure Active Directory ドメインに参加している Windows 10 デバイスと互換性のある Microsoft 以外のクラウド印刷ソリューションを使用します。</span><span class="sxs-lookup"><span data-stu-id="885d2-111">Use a non-Microsoft cloud printing solution that is compatible with Windows 10 devices that are joined to an Azure Active Directory domain.</span></span> <span data-ttu-id="885d2-112">ソリューションは、Microsoft Managed Desktop のソフトウェア要件を満たす必要があります。</span><span class="sxs-lookup"><span data-stu-id="885d2-112">The solution must meet the software requirements for Microsoft Managed Desktop.</span></span> <span data-ttu-id="885d2-113">詳細については [、「Microsoft Managed Desktop アプリの要件」を参照してください](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="885d2-113">For more information, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
 
<span data-ttu-id="885d2-114">すべての場合、プリンター ドライバーが Microsoft Update または Microsoft Store から利用できない場合は、それらを取得し、Microsoft Intune を使用して Microsoft 管理デスクトップ デバイスに展開するためにパッケージ化する必要があります。</span><span class="sxs-lookup"><span data-stu-id="885d2-114">In all cases, if the printer drivers are not available from Microsoft Update or the Microsoft Store, you'll have to obtain them yourself and have them packaged for deployment to your Microsoft Managed Desktop devices with Microsoft Intune.</span></span> <span data-ttu-id="885d2-115">詳細については [、「Intune スタンドアロン - Win32 アプリ管理」を参照してください。](/mem/intune/apps/apps-win32-app-management)</span><span class="sxs-lookup"><span data-stu-id="885d2-115">For more, see [Intune Standalone - Win32 app management](/mem/intune/apps/apps-win32-app-management)</span></span>

## <a name="set-up-local-printers"></a><span data-ttu-id="885d2-116">ローカル プリンターのセットアップ</span><span class="sxs-lookup"><span data-stu-id="885d2-116">Set up local printers</span></span>

<span data-ttu-id="885d2-117">カスタム PowerShell スクリプトを使用してプリンターを展開し、印刷リソースを準備した場合は、次の手順に従って共有プリンターを展開します。</span><span class="sxs-lookup"><span data-stu-id="885d2-117">If you've decided to deploy printers by using a custom PowerShell script and have prepared the printing resources, follow these steps to have shared printers deployed:</span></span>

1.  <span data-ttu-id="885d2-118">Microsoft Managed Desktop ポータルに移動します。</span><span class="sxs-lookup"><span data-stu-id="885d2-118">Navigate to the Microsoft Managed Desktop portal.</span></span>
2.  <span data-ttu-id="885d2-119">次の詳細を提供 *して、管理* ポータルの [サポート >サポート要求] セクションで、プリンターの展開というラベルの付いた要求を送信します。</span><span class="sxs-lookup"><span data-stu-id="885d2-119">Submit a request labeled *Printer deployment* in the **Support > Support requests** section of the Admin Portal, providing these details:</span></span>
    - <span data-ttu-id="885d2-120">Microsoft Managed Desktop デバイスに展開する必要がある共有プリンターの場所へのすべての UNC パス</span><span class="sxs-lookup"><span data-stu-id="885d2-120">All UNC paths to shared printer locations that will need to be deployed for Microsoft Managed Desktop devices</span></span>
    - <span data-ttu-id="885d2-121">これらの共有プリンターへのアクセスを必要とするユーザー グループ</span><span class="sxs-lookup"><span data-stu-id="885d2-121">User groups that require access to these shared printers</span></span>
3.  <span data-ttu-id="885d2-122">管理ポータルを使用して、要求がいつ完了したのかお知らせします。</span><span class="sxs-lookup"><span data-stu-id="885d2-122">Using the Admin Portal, we'll let you know when the request has been completed.</span></span> <span data-ttu-id="885d2-123">最初は、テスト展開グループ内のデバイスにのみ構成を展開します。</span><span class="sxs-lookup"><span data-stu-id="885d2-123">Initially we'll only deploy the configuration to devices in the Test deployment group.</span></span>
4.  <span data-ttu-id="885d2-124">構成が期待通り動作するかどうかをテストして確認する必要があります。</span><span class="sxs-lookup"><span data-stu-id="885d2-124">You must test and confirm whether the configuration works as you expect.</span></span> <span data-ttu-id="885d2-125">サポート要求の [ **ディスカッション]** タブを使用して返信し、テストが完了したらお知らせします。</span><span class="sxs-lookup"><span data-stu-id="885d2-125">Reply by using the **Discussion** tab in the Support request to let us know when you've completed your testing.</span></span>
5.  <span data-ttu-id="885d2-126">その後、構成を他の展開グループに展開します。</span><span class="sxs-lookup"><span data-stu-id="885d2-126">We'll then deploy the configuration to the other deployment groups.</span></span>