---
title: 仮想証明書のコレクションのセットアップ - Exchange Online
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 04a616e6-197c-490c-ae8c-c8d5f0f0b3dd
description: 管理者は、Exchange Online で S/MIME 証明書の検証に使用される仮想証明書コレクションの作成方法を学習できます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 16c6d38882a69feb46aa3e8fadccd6e005426304
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825139"
---
# <a name="set-up-virtual-certificate-collection-in-exchange-online-to-validate-smime"></a><span data-ttu-id="cc547-103">S/MIME を検証するために Exchange Online で仮想証明書のコレクションを設定する</span><span class="sxs-lookup"><span data-stu-id="cc547-103">Set up virtual certificate collection in Exchange Online to validate S/MIME</span></span>

<span data-ttu-id="cc547-104">管理者は、S/MIME 証明書の検証に使用する仮想の証明書コレクションを Exchange Online で構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="cc547-104">As an admin, you will need to configure a virtual certificate collection in Exchange Online that will be used to validate S/MIME certificates.</span></span> <span data-ttu-id="cc547-105">この仮想証明書コレクションは、SST ファイル名拡張子を持つ証明書ストアとしてセットアップされます。</span><span class="sxs-lookup"><span data-stu-id="cc547-105">This virtual certificate collection is set up as a certificate store with an SST filename extension.</span></span> <span data-ttu-id="cc547-106">SST ファイルには、S/MIME 証明書の検証時に使用されるすべてのルート証明書と中間証明書が含まれます。</span><span class="sxs-lookup"><span data-stu-id="cc547-106">The SST file contains all the root and intermediate certificates that are used when validating an S/MIME certificate.</span></span>

## <a name="create-and-save-an-sst"></a><span data-ttu-id="cc547-107">SST を作成して保存する</span><span class="sxs-lookup"><span data-stu-id="cc547-107">Create and save an SST</span></span>

<span data-ttu-id="cc547-108">この SST 証明書ストア ファイルは、Windows PowerShell で **Export-Certificate** コマンドレットを使用して信頼できるコンピューターから証明書をエクスポートし、Type 値を SST _に設定_ して作成できます。</span><span class="sxs-lookup"><span data-stu-id="cc547-108">You can create this SST certificate store file by exporting the certificates from a trusted machine using the **Export-Certificate** cmdlet in Windows PowerShell and specifying the _Type_ value as SST.</span></span> <span data-ttu-id="cc547-109">手順については [、「Export-Certificate」を参照してください](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate)。</span><span class="sxs-lookup"><span data-stu-id="cc547-109">For instructions, see [Export-Certificate](https://docs.microsoft.com/powershell/module/pkiclient/export-certificate).</span></span>

<span data-ttu-id="cc547-110">SST 証明書ストア ファイルを入手した後、Exchange Online PowerShell で次の構文を使用して SST ファイルの内容を Exchange Online 仮想証明書ストアに保存します。</span><span class="sxs-lookup"><span data-stu-id="cc547-110">Once you have the SST certificate store file, use the following syntax in Exchange Online PowerShell to save the SST file contents in the Exchange Online virtual certificate store.</span></span> <span data-ttu-id="cc547-111">Exchange Online PowerShell へ接続するには、「[Exchange Online PowerShell に接続する](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="cc547-111">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content <FileNameAndPath>.sst -Encoding Byte)
```

<span data-ttu-id="cc547-112">この例では、SST ファイル C:\My Documents\Exported Certificate Store.sst をインポートします。</span><span class="sxs-lookup"><span data-stu-id="cc547-112">This example imports the SST file C:\My Documents\Exported Certificate Store.sst.</span></span>

```PowerShell
Set-SmimeConfig -SMIMECertificateIssuingCA (Get-Content "C:\My Documents\Exported Certificate Store.sst" -Encoding Byte)
```

<span data-ttu-id="cc547-113">構文およびパラメーターの詳細については [、「Set-SmimeConfig」を参照してください](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig)。</span><span class="sxs-lookup"><span data-stu-id="cc547-113">For detailed syntax and parameter information, see [Set-SmimeConfig](https://docs.microsoft.com/powershell/module/exchange/set-smimeconfig).</span></span>

## <a name="ensuring-a-certificate-is-valid"></a><span data-ttu-id="cc547-114">証明書が有効なことを確認する</span><span class="sxs-lookup"><span data-stu-id="cc547-114">Ensuring a certificate is valid</span></span>

<span data-ttu-id="cc547-115">Exchange Online では、証明書の検証に使用できるのは SST のみです。</span><span class="sxs-lookup"><span data-stu-id="cc547-115">In Exchange Online, only the SST is used for certificate validation.</span></span>

## <a name="more-information"></a><span data-ttu-id="cc547-116">詳細情報</span><span class="sxs-lookup"><span data-stu-id="cc547-116">More Information</span></span>

[<span data-ttu-id="cc547-117">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="cc547-117">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="cc547-118">Get-SmimeConfig</span><span class="sxs-lookup"><span data-stu-id="cc547-118">Get-SmimeConfig</span></span>](https://docs.microsoft.com/powershell/module/exchange/get-smimeconfig)
