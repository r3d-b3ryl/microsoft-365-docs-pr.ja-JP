---
title: Microsoft Microsoft Projectデスクトップ デバイスにVisioまたは Microsoft のデバイスをインストールする
description: Microsoft Managed Desktop デバイスMicrosoft Projectまたは Microsoft Visioのインストールに関する情報
keywords: Microsoft Managed Desktop、Microsoft 365、Microsoft Project、Microsoft Visio
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: ebba2983e584e3b7d445d8962fb8dc0536d360f3
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034583"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Microsoft Microsoft Projectデスクトップ デバイスにVisioまたは Microsoft のデバイスをインストールする

Microsoft Projectおよび Microsoft Visioは、Microsoft マネージ デスクトップ デバイスにインストールする特定の手順が必要です。 このトピックでは、これらのアプリケーションの前提条件とインストール プロセスについて説明します。

## <a name="prerequisites"></a>前提条件

管理者は、次の前提条件を満たしていることを確認する必要があります。
- **ライセンスの数量**- ユーザーが使用できるMicrosoft Projectライセンスと Microsoft Visioライセンスの正しい量を指定する必要があります。 Microsoft Managed Desktop は現在、これらのアプリケーションの 64 ビット バージョンのみをサポートしています。 
- **ライセンス名** - これらのアプリケーションの適切なライセンス名は次のとおりです。
    - **Microsoft Project** - Project Online ProfessionalまたはProject Online Premium
    - **Microsoft Visio** - Visio オンライン プラン 2
- **ポータル サイト**- ユーザーポータル サイトこれらのアプリケーションをインストールするには、テナントで使用できる必要があります。 テナントにポータル サイト展開されていない場合は、「ポータル サイト」[を参照してください](company-portal.md)。

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Microsoft Project デスクトップ Visioの展開と展開
Microsoft Managed Desktop は、Microsoft Projectと Microsoft Visio Win32 アプリケーションを 2 つのアプリケーションとして追加Microsoft Intune。 また、"Available" インテントAzure Active Directory対応するアプリケーションに割り当てられる 2 つのグループを作成します。 

**アプリケーションをProject展開Visio** ユーザーを適切なグループに追加すると、アプリケーションがアプリケーションで使用ポータル サイト。 同期に数分かかる場合がありますが、ユーザーはアプリをアプリからインストールポータル サイト。 

Azure ADグループ名 | どのユーザーを割り当てるか。   
 --- | ---
モダン Workplace-Office-Project_Install | 必要なユーザー Project
モダン Workplace-Office-Visio_Install | 必要なユーザー Visio

## <a name="communicate-changes"></a>変更を伝える
IT 管理者は、ユーザーにインストール方法とインストール方法をユーザーに知Project重要Visio。 これには以下が含まれます。 
- これらのアプリケーションが使用可能な場合にユーザーに通知します。 
- これらのアプリケーションをインストールする方法については、ポータル サイト。
