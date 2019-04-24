---
title: microsoft Project または microsoft Visio を microsoft マネージドデスクトップデバイスにインストールする
description: microsoft Project または microsoft Visio を microsoft マネージドデスクトップデバイスにインストールするための情報
keywords: microsoft マネージドデスクトップ、microsoft 365、microsoft Project、microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288998"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>microsoft Project または microsoft Visio を microsoft マネージドデスクトップデバイスにインストールする

microsoft Project および microsoft Visio では、microsoft マネージドデスクトップデバイスに特定の手順をインストールする必要があります。 このトピックでは、これらのアプリケーションの前提条件とインストールプロセスについて説明します。

## <a name="prerequisites"></a>前提条件

管理者は、これらの前提条件を満たしていることを確認する必要があります。
- **ライセンス**数-ユーザーが使用できる microsoft Project と microsoft Visio のライセンスの正確な量が必要です。 現在、Microsoft マネージドデスクトップでは、これらのアプリケーションの64ビットバージョンのみがサポートされています。 
- **ライセンス名**-これらのアプリケーションの適切なライセンス名は次のとおりです。
    - **Microsoft project** -project online Professional または project online Premium
    - **Microsoft visio** -visio Online プラン2
- **ポータルサイト**-ユーザーがこれらのアプリケーションをインストールできるようにするには、テナントで会社のポータルを使用できる必要があります。 テナントに会社のポータルが展開されていない場合は、「 [company portal](company-portal.md)」を参照してください。

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Microsoft マネージドデスクトップデバイス用に Project および Visio を展開する
サポート要求を送信した後、microsoft Managed Desktop は、microsoft Intune によって3つの Azure AD グループと3つのアプリケーション展開を作成し、アプリをテナントに展開します。  

**Project と Visio を展開するには**
1. **サポート要求のファイル**IT 管理者は、このようなアプリケーションをユーザーが使用できるようにするためにサポート要求をファイルする必要があります。 microsoft の管理されたデスクトップにアクセスする方法については、「 [microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。
2. **新しい Azure AD グループへのユーザーの割り当て**Microsoft マネージドデスクトップは、テナントに3つの Azure AD グループと、それに対応する3つのアプリケーション展開を作成します。 IT 管理者は、ユーザーを適切なグループに割り当てる必要があります。

>[!NOTE]
>ユーザーは、これらのいずれかの Azure AD グループにのみ割り当ててください。 

Azure AD グループ名 | 割り当てるユーザー   
 --- | ---
Microsoft-Office-Project-インストール | プロジェクトのみを必要とするユーザー
Microsoft-Office-Visio-インストール | Visio のみを必要とするユーザー
Microsoft-Office-Project および Visio-インストール | Project と Visio の両方を必要とするユーザー

これらのグループに割り当てられると、アプリケーションは会社のポータルで利用できるようになります。 同期には数分かかる場合がありますが、ユーザーは会社のポータルからアプリをインストールできます。 

## <a name="communicate-changes"></a>変更の伝達
it 管理者は、プロジェクトと Visio をインストールする方法をユーザーに知らせることが重要です。 これには以下が含まれます。 
- これらのアプリケーションが利用可能な場合にユーザーに通知します。 
- これらのアプリケーションをポータルサイトからインストールする方法について説明します。

>[!NOTE]
>ユーザーは、microsoft Project または会社のポータルから microsoft Visio をインストールする前に、すべての Office アプリケーションを閉じる必要があります。 
