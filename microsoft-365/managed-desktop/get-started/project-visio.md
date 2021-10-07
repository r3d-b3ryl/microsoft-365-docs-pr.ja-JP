---
title: デバイスにMicrosoft Projectまたは Microsoft VisioをMicrosoft マネージド デスクトップする
description: デバイスへのMicrosoft Projectまたは Microsoft VisioのMicrosoft マネージド デスクトップ情報
keywords: Microsoft マネージド デスクトップ、Microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: medium
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: af5470d0993c54c1593526a7e0e3ae0b6e239065
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60199791"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>デバイスにMicrosoft Projectまたは Microsoft VisioをMicrosoft マネージド デスクトップする

Microsoft Project Microsoft Visioデバイスにインストールするには、特定の手順Microsoft マネージド デスクトップ必要があります。 このトピックでは、これらのアプリケーションの前提条件とインストール プロセスについて説明します。

## <a name="prerequisites"></a>前提条件

管理者は、次の前提条件を満たしていることを確認する必要があります。
- **ライセンスの数量**- ユーザーが使用できるMicrosoft Projectライセンスと Microsoft Visioライセンスの正しい量を指定する必要があります。 Microsoft マネージド デスクトップ現在、これらのアプリケーションの 64 ビット バージョンのみをサポートしています。 
- **ライセンス名** - これらのアプリケーションの適切なライセンス名は次のとおりです。
    - **Microsoft Project** - Project Online ProfessionalまたはProject Online Premium
    - **Microsoft Visio** - Visio オンライン プラン 2
- **ポータル サイト**- ユーザーポータル サイトこれらのアプリケーションをインストールするには、テナントで使用できる必要があります。 テナントにポータル サイト展開されていない場合は、「ポータル サイト」[を参照してください](company-portal.md)。

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>デバイスProjectのVisioとMicrosoft マネージド デスクトップ展開
Microsoft マネージド デスクトップは、Microsoft Project Win32 アプリケーションVisio Win32 アプリケーションとして追加Microsoft Intune。 また、"Available" インテントAzure Active Directory対応するアプリケーションに割り当てられる 2 つのグループを作成します。 

**サーバーとProjectを展開Visio** ユーザーを適切なグループに追加すると、アプリケーションがアプリケーションで使用ポータル サイト。 同期に数分かかる場合がありますが、ユーザーはアプリをアプリからインストールポータル サイト。 

Azure AD グループ名 | どのユーザーを割り当てるか。   
 --- | ---
モダン Workplace-Office-Project_Install | 必要なユーザー Project
モダン Workplace-Office-Visio_Install | 必要なユーザー Visio

## <a name="communicate-changes"></a>変更を伝える
IT 管理者は、ユーザーにインストール方法とインストール方法をユーザーに知Project重要Visio。 これには、次の内容が含まれます。 
- これらのアプリケーションが使用可能な場合にユーザーに通知します。 
- これらのアプリケーションをインストールする方法については、ポータル サイト。
