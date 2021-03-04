---
title: iOS の Office アプリをセキュリティで保護する
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Microsoft 365 Business Premium Officeアプリを保護する方法について説明します。
ms.openlocfilehash: 197041a4eb9ada65f4b6046d93f2a856cbdfb40d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422113"
---
# <a name="secure-office-apps-on-ios"></a>iOS の Office アプリをセキュリティで保護する

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

モバイル ユーザーがサインインする PIN または指紋を入力する必要があるユーザー アクセス ポリシーを設定し、デバイスに保存されている作業ファイルも暗号化できます。

## <a name="try-it"></a>演習

1. Microsoft 365 管理センターにサインインします。
1. [ポリシー **] で、[** ポリシーの **追加] を選択します**。
1. [ポリシーの **追加] ウィンドウ** で、[ポリシー名] に名前を入力し、[ポリシーの種類] で必要なポリシーの種類 **を選択します**。
1. [ユーザーが **モバイル デバイス上のOfficeファイル** にアクセスする方法を管理する] をオンにし、次の 3 つの設定がオンになっていることを確認します。
    - **Office アプリにアクセスするのに暗証番号 (PIN) または指紋認証を使用する必要がある**
    - **デバイスが紛失または盗まれたときに作業ファイルを保護する**
    - **仕事用ファイルを暗号化する**

1. [ **これらのアプリのファイルが保護されます**] で、モバイル Office保護するアプリを選択します。
1. [**これらの設定を取得するユーザー]** で、すべてのユーザーが既定で選択されますが、[変更] を選択して、作成したセキュリティ グループを選択できます。
1. ポリシーの作成を完了するには、[追加] を **選択します**。
1. [ポリシーの **追加] ページで** 、[閉じる] を **選択します**。
1. 管理センターのホーム ページで、[ポリシー] を選択し、[ポリシー]ページでポリシーを確認して、新しいポリシーが **追加されたと確認** します。