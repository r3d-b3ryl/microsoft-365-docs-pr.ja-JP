---
title: Microsoft Project または microsoft Visio を Microsoft マネージドデスクトップデバイスにインストールする
description: Microsoft Project または microsoft Visio を Microsoft マネージドデスクトップデバイスにインストールするための情報
keywords: Microsoft マネージドデスクトップ、Microsoft 365、microsoft Project、Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 450dbcb08cd0636dae575ecd2d5e9abadc5ceb25
ms.sourcegitcommit: 44e685a0b193e89de5befb1e1a3740eb31931799
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/05/2020
ms.locfileid: "44022098"
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
サポート要求を送信した後、Microsoft Managed Desktop は、Microsoft Intune によって3つの Azure AD グループと3つのアプリケーション展開を作成し、アプリをテナントに展開します。  

**Project と Visio を展開するには**
1. **サポート要求のファイル**IT 管理者は、このようなアプリケーションをユーザーが使用できるようにするためにサポート要求をファイルする必要があります。 Microsoft の管理されたデスクトップにアクセスする方法については、「 [Microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。
2. **新しい AZURE AD グループへのユーザーの割り当て**Microsoft マネージドデスクトップは、テナントに3つの Azure AD グループと、それに対応する3つのアプリケーション展開を作成します。 IT 管理者は、ユーザーを適切なグループに割り当てる必要があります。

>[!NOTE]
>ユーザーは、これらのいずれかの Azure AD グループにのみ割り当ててください。 

Azure AD グループ名 | 割り当てるユーザー   
 --- | ---
モダンワークプレース-Office-Project_Install | プロジェクトを必要とするユーザー
モダンワークプレース-Office-Visio_Install | Visio を必要とするユーザー

これらのグループに割り当てられると、アプリケーションは会社のポータルで利用できるようになります。 同期には数分かかる場合がありますが、ユーザーは会社のポータルからアプリをインストールできます。 

## <a name="communicate-changes"></a>変更の伝達
IT 管理者は、プロジェクトと Visio をインストールする方法をユーザーに知らせることが重要です。 これには以下が含まれます。 
- これらのアプリケーションが利用可能な場合にユーザーに通知します。 
- これらのアプリケーションをポータルサイトからインストールする方法について説明します。

>[!NOTE]
>ユーザーは、Microsoft Project または会社のポータルから Microsoft Visio をインストールする前に、すべての Office アプリケーションを閉じる必要があります。 
