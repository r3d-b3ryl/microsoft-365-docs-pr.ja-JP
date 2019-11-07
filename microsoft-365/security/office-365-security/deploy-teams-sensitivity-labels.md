---
title: 機密ラベルを使用してチーム内のファイルを保護する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 10/31/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- Ent_Solutions
ms.assetid: 5b9c8e41-25d2-436d-89bb-9aecb9ec2b80
description: '概要: 機密ラベルを適用して、機密性の高いチーム内のファイルを保護します。'
ms.openlocfilehash: f52b864087d22e14bb3e9bfe1eb38d088f6f981a
ms.sourcegitcommit: 33242c260439de0d8db41247e9414913f24adc22
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925827"
---
# <a name="protect-files-in-teams-with-sensitivity-labels"></a><span data-ttu-id="5864c-103">機密ラベルを使用してチーム内のファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="5864c-103">Protect files in teams with sensitivity labels</span></span>


<span data-ttu-id="5864c-104">すべてのユーザーが任意のファイルに適用できる、厳しく規制されたデータの機密ラベルとは異なり、機密性の高いチームでは独自のラベルまたはサブラベルが必要です。それらが割り当てられたファイルは次のようになります。</span><span class="sxs-lookup"><span data-stu-id="5864c-104">Unlike a sensitivity label for highly regulated data that anyone can apply to any file, a secure team needs its own label or sublabel so that assigned files:</span></span>

- <span data-ttu-id="5864c-105">個別に暗号化される。</span><span class="sxs-lookup"><span data-stu-id="5864c-105">Are individually encrypted.</span></span>
- <span data-ttu-id="5864c-106">チームのメンバーのみがファイルを開けるように、カスタムのアクセス許可が含まれる。</span><span class="sxs-lookup"><span data-stu-id="5864c-106">Contain custom permissions so that only members of the Team Group can open it.</span></span>

<span data-ttu-id="5864c-107">チームの基礎となる SharePoint サイトに保存されているファイルに対してこの追加レベルのセキュリティ保護を行うには、サイト独自のラベル、または厳しく規制されたデータの一般的なラベルのサブラベルのいずれかである、カスタマイズされた機密ラベルを構成する必要があります。</span><span class="sxs-lookup"><span data-stu-id="5864c-107">To accomplish this additional level of security for files stored in the Team Site, you must configure a new sensitivity label that is either its own label a sublabel of the general label for highly regulated files.</span></span> <span data-ttu-id="5864c-108">ラベルのリストにあるカスタマイズされたラベルまたはサブラベルは、チーム メンバーにのみ表示されます。</span><span class="sxs-lookup"><span data-stu-id="5864c-108">Only team members will see the customized label or sublabel in their list of labels.</span></span>

<span data-ttu-id="5864c-109">全体での使用と個別のプライベート チームの両方に対して少ない数のラベルが必要な場合は、機密ラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="5864c-109">Use a sensitivity label when you need a small number of labels for both global use and individual private teams.</span></span> 

<span data-ttu-id="5864c-110">ラベルを多数使用している場合、または機密性の高いチーム用のラベルを厳しく規制されたラベルの下でまとめる場合は、機密サブラベルを使用します。</span><span class="sxs-lookup"><span data-stu-id="5864c-110">Use a sensitivity sublabel when you have a large number of labels or want to organize labels for private teams under the highly regulated label.</span></span>

<span data-ttu-id="5864c-111">[こちらの手順](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)を使用して、別のラベルまたはサブラベルを次の設定で構成します。</span><span class="sxs-lookup"><span data-stu-id="5864c-111">[Use these instructions](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels) to configure a separate label or a sublabel with the following settings:</span></span>

- <span data-ttu-id="5864c-112">ラベルまたはサブラベルの名前に、チームの名前が含まれている</span><span class="sxs-lookup"><span data-stu-id="5864c-112">The name of the label contains the name of the team</span></span>
- <span data-ttu-id="5864c-113">暗号化が有効になっている</span><span class="sxs-lookup"><span data-stu-id="5864c-113">Encryption is enabled</span></span>
- <span data-ttu-id="5864c-114">チームの Office 365 グループに、共同作成者のアクセス許可が与えられている</span><span class="sxs-lookup"><span data-stu-id="5864c-114">The Office 365 group for the team has Co-Author permissions</span></span>

<span data-ttu-id="5864c-115">作成した後、ユーザーのために新しいラベルまたはサブラベルを発行します。ユーザーは、それらをローカルでチームにアップロードする前、またはチームに保存された後にファイルに適用できます。</span><span class="sxs-lookup"><span data-stu-id="5864c-115">After creating, publish the new label or sublabel for your users, who can then apply them to files either locally before uploading them to the team or later once the file is stored in the team.</span></span>

<span data-ttu-id="5864c-116">ファイルの暗号化とアクセス許可に機密ラベルを使用する機密性の高いチームの構成は、次のとおりです。</span><span class="sxs-lookup"><span data-stu-id="5864c-116">Here is the configuration of the highly confidential team that uses sensitivity labels for file encryption and permissions.</span></span>

![パブリック チームのベースライン レベルの保護。](../media/highly-confidential-team-dlp-sensitivity-labels.png)


## <a name="see-also"></a><span data-ttu-id="5864c-118">関連項目</span><span class="sxs-lookup"><span data-stu-id="5864c-118">See Also</span></span>

[<span data-ttu-id="5864c-119">Microsoft Teams のファイルを保護する</span><span class="sxs-lookup"><span data-stu-id="5864c-119">Secure files in Microsoft Teams</span></span>](secure-files-in-teams.md)
  
[<span data-ttu-id="5864c-120">クラウド導入およびハイブリッド ソリューション</span><span class="sxs-lookup"><span data-stu-id="5864c-120">Cloud adoption and hybrid solutions</span></span>](https://docs.microsoft.com/office365/enterprise/cloud-adoption-and-hybrid-solutions)
