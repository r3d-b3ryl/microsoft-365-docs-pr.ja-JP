---
title: S/MIME 用にユーザー証明書を Office 365 に同期させる
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: 12/09/2016
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 351c932e-99c1-4512-a6e8-788e90b7838f
ms.custom:
- seo-marvel-apr2020
description: この記事では、S/MIME で保護されたメッセージを Exchange Online で送信する前に、Office 365 に適切な証明書を発行する方法について説明します。
ms.openlocfilehash: 3551dbacc3cc6279d319860f1133d059216ae591
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202105"
---
# <a name="sync-user-certificates-to-office-365-for-smime"></a><span data-ttu-id="48a6a-103">S/MIME 用にユーザー証明書を Office 365 に同期する</span><span class="sxs-lookup"><span data-stu-id="48a6a-103">Sync user certificates to Office 365 for S/MIME</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="48a6a-104">すべてのユーザーが S/MIME で保護されたメッセージを Exchange Online で送信できるようにするには、適切な証明書をセットアップする必要があります。</span><span class="sxs-lookup"><span data-stu-id="48a6a-104">Before anyone can send S/MIME-protected messages in Exchange Online, the appropriate certificates must be set up.</span></span> <span data-ttu-id="48a6a-105">Exchange Online を介して暗号化されたメッセージを送信する場合、送信者の電子メールアプリは受信者のパブリック証明書を使用してメッセージを暗号化します。</span><span class="sxs-lookup"><span data-stu-id="48a6a-105">To send encrypted messages through Exchange Online, the sender's email app uses the public certificate of the recipient to encrypt the message.</span></span> <span data-ttu-id="48a6a-106">この公開 X.509 証明書を Office 365 に公開する必要があります。</span><span class="sxs-lookup"><span data-stu-id="48a6a-106">This public X.509 certificate has to be published to Office 365.</span></span>

## <a name="to-sync-certificates-that-support-smime"></a><span data-ttu-id="48a6a-107">S/MIME をサポートする証明書を同期するには</span><span class="sxs-lookup"><span data-stu-id="48a6a-107">To Sync certificates that support S/MIME</span></span>

<span data-ttu-id="48a6a-108">証明書を発行して、ローカルの Active Directory ドメイン サービスで公開することによって、S/MIME のセットアップを開始します。</span><span class="sxs-lookup"><span data-stu-id="48a6a-108">Begin setting up S/MIME by issuing certificates and publishing them in your local Active Directory Domain Service.</span></span> <span data-ttu-id="48a6a-109">詳細については、「[Active Directory 証明書サービスの概要](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11))」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48a6a-109">For more information, see [Active Directory Certificate Services Overview](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831740(v=ws.11)).</span></span>

<span data-ttu-id="48a6a-110">証明書が公開されたら、Azure AD Connect ツールを使用してオンプレミスの Exchange 環境から Office 365 にユーザーデータを同期します。</span><span class="sxs-lookup"><span data-stu-id="48a6a-110">After your certificates are published, use the Azure AD Connect tool to synchronize user data from your on-premises Exchange environment to Office 365.</span></span> <span data-ttu-id="48a6a-111">このプロセスの詳細については、「 [AZURE AD Connect sync: 同期の理解とカスタマイズ](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis)」を参照してください。</span><span class="sxs-lookup"><span data-stu-id="48a6a-111">For more information on this process, see [Azure AD Connect sync: Understand and customize synchronization](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-whatis).</span></span>

<span data-ttu-id="48a6a-112">S/MIME 用に他のディレクトリデータを同期することに加えて、ツールは各ユーザーオブジェクトの  **Usercertificate** 属性と **userSMIMECertificate** 属性を同期し、データを使用してメッセージの署名と暗号化を行うことができるようにします。</span><span class="sxs-lookup"><span data-stu-id="48a6a-112">Along with synchronizing other directory data, for S/MIME purposes, the tool will synchronize the  **userCertificate** and **userSMIMECertificate** attributes for each user object so the data can be used to sign and encrypt messages.</span></span>

## <a name="more-information"></a><span data-ttu-id="48a6a-113">詳細情報</span><span class="sxs-lookup"><span data-stu-id="48a6a-113">More Information</span></span>

[<span data-ttu-id="48a6a-114">S/MIME によるメッセージの署名と暗号化</span><span class="sxs-lookup"><span data-stu-id="48a6a-114">S/MIME for message signing and encryption</span></span>](s-mime-for-message-signing-and-encryption.md)

[<span data-ttu-id="48a6a-115">Azure AD Connect とは?</span><span class="sxs-lookup"><span data-stu-id="48a6a-115">What is Azure AD Connect?</span></span>](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect)
