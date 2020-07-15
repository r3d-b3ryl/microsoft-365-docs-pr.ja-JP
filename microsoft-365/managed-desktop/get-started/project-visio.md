---
title: Microsoft Project または microsoft Visio を Microsoft マネージドデスクトップデバイスにインストールする
description: Microsoft Project または microsoft Visio を Microsoft マネージドデスクトップデバイスにインストールするための情報
keywords: Microsoft マネージドデスクトップ、Microsoft 365、microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c8690db17c71fd5ce604fd9165fee7e54a41c639
ms.sourcegitcommit: e8b9a4f18330bc09f665aa941f1286436057eb28
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/14/2020
ms.locfileid: "45126829"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft Project または microsoft Visio を Microsoft マネージドデスクトップデバイスにインストールする

Microsoft Project および Microsoft Visio では、Microsoft マネージドデスクトップデバイスに特定の手順をインストールする必要があります。 このトピックでは、これらのアプリケーションの前提条件とインストールプロセスについて説明します。

## <a name="prerequisites"></a>前提条件

管理者は、これらの前提条件を満たしていることを確認する必要があります。
- **ライセンス**数-ユーザーが使用できる microsoft Project と microsoft Visio のライセンスの正確な量が必要です。 現在、Microsoft マネージドデスクトップでは、これらのアプリケーションの64ビットバージョンのみがサポートされています。 
- **ライセンス名**-これらのアプリケーションの適切なライセンス名は次のとおりです。
    - **Microsoft project** -Project online Professional または Project online Premium
    - **Microsoft visio** -Visio Online プラン2
- **ポータルサイト**-ユーザーがこれらのアプリケーションをインストールできるようにするには、テナントで会社のポータルを使用できる必要があります。 テナントに会社のポータルが展開されていない場合は、「 [Company portal](company-portal.md)」を参照してください。

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Microsoft マネージドデスクトップデバイス用に Project および Visio を展開する
Microsoft マネージドデスクトップでは、microsoft Project と Microsoft Visio を2つの Win32 アプリケーションとして Microsoft Intune に追加します。 また、「使用可能」の目的で対応するアプリケーションに割り当てられる、Azure Active Directory で2つのグループを作成します。 

**Project と Visio を展開するには**ユーザーを適切なグループに追加すると、アプリケーションが会社のポータルで利用できるようになります。 同期には数分かかる場合がありますが、ユーザーは会社のポータルからアプリをインストールできます。 

Azure AD グループ名 | 割り当てるユーザー   
 --- | ---
モダンワークプレース-Office-Project_Install | プロジェクトを必要とするユーザー
モダンワークプレース-Office-Visio_Install | Visio を必要とするユーザー

## <a name="communicate-changes"></a>変更の伝達
IT 管理者は、プロジェクトと Visio をインストールする方法をユーザーに知らせることが重要です。 保持されるデータには以下が含まれます。 
- これらのアプリケーションが利用可能な場合にユーザーに通知します。 
- これらのアプリケーションをポータルサイトからインストールする方法について説明します。
