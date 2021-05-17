---
title: Microsoft マネージ デスクトップ デバイスに Microsoft Project または Microsoft Visio をインストールする
description: Microsoft マネージ デスクトップ デバイスへの Microsoft Project または Microsoft Visio のインストールに関する情報
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950534"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft マネージ デスクトップ デバイスに Microsoft Project または Microsoft Visio をインストールする

Microsoft Project と Microsoft Visio では、Microsoft Managed Desktop デバイスにインストールする特定の手順が必要です。 このトピックでは、これらのアプリケーションの前提条件とインストール プロセスについて説明します。

## <a name="prerequisites"></a>前提条件

管理者は、次の前提条件を満たしていることを確認する必要があります。
- **ライセンスの数量** - ユーザーが使用できる Microsoft Project ライセンスと Microsoft Visio ライセンスの正しい量が必要です。 Microsoft Managed Desktop は現在、これらのアプリケーションの 64 ビット バージョンのみをサポートしています。 
- **ライセンス名** - これらのアプリケーションの適切なライセンス名は次のとおりです。
    - **Microsoft Project** - Project Online Professional または Project Online Premium
    - **Microsoft Visio** - Visio Online プラン 2
- **ポータル サイト** - ユーザーがこれらのアプリケーションをインストールするには、テナントでポータル サイトを使用できる必要があります。 ポータル サイトがテナントに展開されていない場合は、「ポータル サイト」を [参照してください](company-portal.md)。

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Microsoft Managed Desktop デバイス用の Project と Visio の展開
Microsoft Managed Desktop は、Microsoft Project と Microsoft Visio を Microsoft Intune で 2 つの Win32 アプリケーションとして追加します。 また、Azure Active Directory に 2 つのグループを作成し、"Available" インテントを使用して対応するアプリケーションに割り当てられます。 

**Project と Visio を展開するには** ユーザーを適切なグループに追加すると、アプリケーションはポータル サイトで使用できます。 同期に数分かかる場合がありますが、ユーザーはポータル サイトからアプリをインストールできます。 

Azure AD グループ名 | どのユーザーを割り当てるか。   
 --- | ---
モダン Workplace-Office-Project_Install | Project が必要なユーザー
モダン Workplace-Office-Visio_Install | Visio が必要なユーザー

## <a name="communicate-changes"></a>変更を伝える
IT 管理者は、Project と Visio のインストール方法をユーザーに知らせすることが重要です。 これには、次の内容が含まれます。 
- これらのアプリケーションが使用可能な場合にユーザーに通知します。 
- ポータル サイトからこれらのアプリケーションをインストールする方法について説明します。
