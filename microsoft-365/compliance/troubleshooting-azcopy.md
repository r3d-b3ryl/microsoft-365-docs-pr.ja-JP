---
title: AzCopy のトラブルシューティング (Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Azure AzCopy のエラーのトラブルシューティングを行い、Office 365修復用のデータを読み込Advanced eDiscovery。
ms.custom:
- seo-marvel-mar2020
- seo-marvel-apr2020
ms.openlocfilehash: f34b47762601a3cc66b46fd8a2691c0fb87d3354
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919293"
---
# <a name="troubleshoot-azcopy-in-advanced-ediscovery"></a><span data-ttu-id="fd336-103">AzCopy のトラブルシューティング (Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="fd336-103">Troubleshoot AzCopy in Advanced eDiscovery</span></span>

<span data-ttu-id="fd336-104">Advanced eDiscovery でエラー修復のために Microsoft 365 以外のデータまたはドキュメントを読み込む場合、ユーザー インターフェイスは、アップロードするファイルの保存場所とファイルのアップロード先の Azure ストレージの場所を含むパラメーターを含む Azure AzCopy コマンドを提供します。</span><span class="sxs-lookup"><span data-stu-id="fd336-104">When loading non-Microsoft 365 data or documents for error remediation in Advanced eDiscovery, the user interface supplies an Azure AzCopy command that contains parameters with the location of where the files that you want to upload are stored and the Azure storage location that the files will be uploaded to.</span></span> <span data-ttu-id="fd336-105">ドキュメントをアップロードするには、このコマンドをコピーし、ローカル コンピューターのコマンド プロンプトで実行します。</span><span class="sxs-lookup"><span data-stu-id="fd336-105">To upload your documents, you copy this command and then run it in a Command Prompt on your local computer.</span></span>  <span data-ttu-id="fd336-106">次のスクリーンショットは、AzCopy コマンドの例を示しています。</span><span class="sxs-lookup"><span data-stu-id="fd336-106">The follow screenshot shows an example of an AzCopy command:</span></span>

![アップロードファイル以外Microsoft 365ファイル](../media/46ba68f6-af11-4e70-bb91-5fc7973516e3.png)

<span data-ttu-id="fd336-108">通常、指定されたコマンドは、実行時に機能します。</span><span class="sxs-lookup"><span data-stu-id="fd336-108">Usually the command that's provided works when you run it.</span></span> <span data-ttu-id="fd336-109">ただし、表示されるコマンドが正常に実行されない場合があります。</span><span class="sxs-lookup"><span data-stu-id="fd336-109">However, there may be cases when the command that's displayed will not run successfully.</span></span> <span data-ttu-id="fd336-110">考えられる理由を次に示します。</span><span class="sxs-lookup"><span data-stu-id="fd336-110">Here's a few possible reasons.</span></span>

## <a name="the-supported-version-of-azcopy-isnt-installed-on-the-local-computer"></a><span data-ttu-id="fd336-111">サポートされているバージョンの AzCopy がローカル コンピューターにインストールされていない</span><span class="sxs-lookup"><span data-stu-id="fd336-111">The supported version of AzCopy isn't installed on the local computer</span></span>

<span data-ttu-id="fd336-112">この時点で、AzCopy v8.1 を使用して、データを読み込むMicrosoft 365必要Advanced eDiscovery。</span><span class="sxs-lookup"><span data-stu-id="fd336-112">At this time, you must use AzCopy v8.1 to load non-Microsoft 365 data in Advanced eDiscovery.</span></span> <span data-ttu-id="fd336-113">前のスクリーンショットに示した [アップロードファイル] ページに表示される AzCopy コマンドは、AzCopy v8.1 を使用していない場合にエラーを返します。</span><span class="sxs-lookup"><span data-stu-id="fd336-113">The AzCopy command that's displayed on the **Upload files** page shown in the previous screenshot returns an error if you're not using AzCopy v8.1.</span></span> <span data-ttu-id="fd336-114">このバージョンをインストールするには[、「AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)を使用してデータを転送する」を参照Windows。</span><span class="sxs-lookup"><span data-stu-id="fd336-114">To install this version, see [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span>

## <a name="azcopy-isnt-installed-on-the-local-computer-or-its-not-installed-in-the-default-location"></a><span data-ttu-id="fd336-115">AzCopy がローカル コンピューターにインストールされていないか、既定の場所にインストールされていない</span><span class="sxs-lookup"><span data-stu-id="fd336-115">AzCopy isn't installed on the local computer or it's not installed in the default location</span></span>

<span data-ttu-id="fd336-116">AzCopy がインストールされていないか、既定のインストール場所 (つまり) 以外の場所にインストールされている場合は、AzCopy コマンドを実行すると、次のエラー メッセージが `%ProgramFiles(x86)%` 表示される場合があります。</span><span class="sxs-lookup"><span data-stu-id="fd336-116">If AzCopy isn't installed or it's installed in a location other than the default install location (which is `%ProgramFiles(x86)%`), you may receive the following error when you run the AzCopy command:</span></span>

> <span data-ttu-id="fd336-117">システムは、指定されたパスを見つけ出す必要があります。</span><span class="sxs-lookup"><span data-stu-id="fd336-117">The system cannot find the path specified.</span></span>

<span data-ttu-id="fd336-118">AzCopy がローカル コンピューターにインストールされていない場合は、「データの転送」の[「AzCopy v8.1](/previous-versions/azure/storage/storage-use-azcopy)を使用してデータを転送する」を参照Windows。</span><span class="sxs-lookup"><span data-stu-id="fd336-118">If AzCopy isn't installed on the local computer, you can find installation information in [Transfer data with the AzCopy v8.1 on Windows](/previous-versions/azure/storage/storage-use-azcopy).</span></span> <span data-ttu-id="fd336-119">既定の場所にインストールしてください。</span><span class="sxs-lookup"><span data-stu-id="fd336-119">Be sure to install it in the default location.</span></span>

<span data-ttu-id="fd336-120">AzCopy がインストールされているが、既定の場所とは異なる場所にインストールされている場合は、コマンドをコピーしてテキスト ファイルに貼り付け、パスを AzCopy がインストールされている場所に変更できます。</span><span class="sxs-lookup"><span data-stu-id="fd336-120">If AzCopy is installed, but it's installed in a location different than the default location, you can copy the command, paste it to a text file, and then change the path to the location where AzCopy is installed.</span></span> <span data-ttu-id="fd336-121">たとえば、Azcopy がにある場合は、コマンドの最初の部分をに `%ProgramFiles%` 変更 `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` できます `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy` 。</span><span class="sxs-lookup"><span data-stu-id="fd336-121">For example, if Azcopy is located in `%ProgramFiles%`, then you can change the first part of the command from `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy.exe` to `%ProgramFiles%\Microsoft SDKs\Azure\AzCopy`.</span></span> <span data-ttu-id="fd336-122">この変更を行った後、テキスト ファイルからコピーし、コマンド プロンプトを実行します。</span><span class="sxs-lookup"><span data-stu-id="fd336-122">After you make this change, copy it from the text file and then run it a Command Prompt.</span></span>

> [!TIP]
> <span data-ttu-id="fd336-123">AzCopy が別の場所にインストールされている場合は、既定のインストール場所をアンインストールしてから、既定の場所に再インストールしてください。</span><span class="sxs-lookup"><span data-stu-id="fd336-123">If AzCopy is installed in a location other then the default install location, consider uninstalling it and then re-installing it in the default location.</span></span> <span data-ttu-id="fd336-124">これは、将来この問題を防ぐのに役立ちます。</span><span class="sxs-lookup"><span data-stu-id="fd336-124">This will help prevent this issue in the future.</span></span>