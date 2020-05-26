---
title: 仮想証明書コレクションのセットアップ-Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 管理者は、Exchange Online で S/MIME 証明書の検証に使用する仮想証明書コレクションを作成する方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5bd453383a263fdb2c0c7e2ce0014ad205e5fdc2
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352171"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="ae733-103">S/MIME を検証するために Exchange Online で仮想証明書コレクションをセットアップする</span><span class="sxs-lookup"><span data-stu-id="ae733-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="ae733-104">管理者は、S/MIME 証明書の検証に使用する Exchange Online の仮想証明書コレクションを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="ae733-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="ae733-105">この仮想証明書コレクションは、SST ファイル拡張子を持つ証明書ストアとして設定されます。</span><span class="sxs-lookup"><span data-stu-id="ae733-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="ae733-106">SST ファイルには、S/MIME 証明書の検証時に使用されるすべてのルート証明書と中間証明書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="ae733-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="ae733-107">SST を作成して保存する</span><span class="sxs-lookup"><span data-stu-id="ae733-107">Create and save an SST</span></span>

<span data-ttu-id="ae733-108">この SST 証明書ストアファイルは、Windows PowerShell で**証明書のエクスポート**コマンドレットを使用して信頼できるコンピューターから証明書をエクスポートし、 _Type_の値を SST として指定することによって作成できます。</span><span class="sxs-lookup"><span data-stu-id="ae733-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="ae733-109">手順については、「 [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae733-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="ae733-110">SST 証明書ストアファイルを取得したら、Exchange Online PowerShell で次の構文を使用して、Exchange Online 仮想証明書ストアに SST ファイルの内容を保存します。</span><span class="sxs-lookup"><span data-stu-id="ae733-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="ae733-111">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae733-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="ae733-112">この例では、SST ファイル C:\My Documents\Exported 証明書ストア SST をインポートします。</span><span class="sxs-lookup"><span data-stu-id="ae733-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="ae733-113">構文およびパラメーターの詳細については、「 [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="ae733-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="ae733-114">証明書が有効なことを確認する</span><span class="sxs-lookup"><span data-stu-id="ae733-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="ae733-115">Exchange Online では、証明書の検証に SST のみが使用されます。</span><span class="sxs-lookup"><span data-stu-id="ae733-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="ae733-116">詳細情報</span><span class="sxs-lookup"><span data-stu-id="ae733-116">More Information</span></span>

[<span data-ttu-id="ae733-117">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="ae733-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="ae733-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="ae733-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
