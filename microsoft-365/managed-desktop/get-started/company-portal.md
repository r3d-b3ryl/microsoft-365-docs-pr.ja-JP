---
title: デバイスIntune ポータル サイトインストールする
description: ポータル サイト アプリをデバイスにインストールするMicrosoft マネージド デスクトップ情報
keywords: Microsoft マネージド デスクトップ、Microsoft 365、ポータル サイト
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 57f4d05089a023b5f64f0e27a8e0a20305a02a06
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208723"
---
# <a name="install-intune-company-portal-on-devices"></a>デバイスIntune ポータル サイトインストールする

Microsoft マネージド デスクトップ IT 管理者は、ユーザーがデバイスを使用Intune ポータル サイトユーザー用にMicrosoft マネージド デスクトップする必要があります。 組織の利点を次に示します。
- ユーザーは、使用可能なアプリケーションを参照してインストールする場所を 1 つ持っています。 
- IT 管理者は、ユーザーのカテゴリ別にアプリケーションを整理できます。  
- 一部のアプリケーション (Microsoft Project Microsoft Visioなど) では、ポータル サイトを使用して展開する必要Microsoft マネージド デスクトップ。
- IT 管理者は、組織ポータル サイトをカスタマイズできます。 これには、ブランドイメージング、ローカル サポート連絡先の追加などです。 詳細については、「How [to Configure the Microsoft Intune ポータル サイト App 」を参照してください](/intune/company-portal-app)。   

このトピックでは、ユーザーにアプリケーションを展開Intune ポータル サイトプロセスMicrosoft マネージド デスクトップ説明します。 全体的なプロセスは次のように表示されます。
1. Intune ポータル サイトからビジネス向け Microsoft Storeを購入して同期する
2. ユーザーポータル サイト割り当てる
3. 変更をユーザーに伝える

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>手順 1 - Intune からポータル サイトをビジネス向け Microsoft Store Intune と同期する
アプリを購入して Intune と同期する方法については、「アプリ [](deploy-apps.md#msfb-apps)をデバイスにビジネス向け Microsoft Storeする」*をMicrosoft マネージド デスクトップしてください*。

このトピックでは、次の方法について説明します。 
- 購入ポータル サイトからビジネス向け Microsoft Store 
- Intune とデバイス間の強制的な同期ビジネス向け Microsoft Store
- Intune とデバイス間のアクティブな同期を確認ビジネス向け Microsoft Store 

## <a name="step-2---assign-company-portal-to-your-users"></a>手順 2 - ユーザーにポータル サイトを割り当てる
ユーザーの登録にMicrosoft マネージド デスクトップ、テナントにポータル サイトを自動的に展開し、組織内Microsoft マネージド デスクトップデバイスにアプリをインストールします。

## <a name="step-3---communicate-change-to-your-users"></a>手順 3 - ユーザーに変更を伝える
組織の IT 管理者として、組織のユーザーに組織の管理者のポータル サイト知らせすることが重要です。 Microsoft マネージド デスクトップをお勧めします。
- アプリケーションをインストールする手順については、ポータル サイト。 詳細については、「デバイスにアプリ [をインストールして共有する」を参照してください](/intune-user-help/install-apps-cpapp-windows)。
- 現在利用できないアプリケーションの要求を IT 管理者に送信する方法。 詳細については、「アプリを [仕事または学校に依頼する」を参照してください](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>データの使用を開始するMicrosoft マネージド デスクトップ

1. [管理ポータル](access-admin-portal.md)にアクセスします。
1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)。
1. [登録後に設定を調整する](conditional-access.md)。
1. この記事では、Intune ポータル サイトを展開して割り当てる。
1. [ライセンスを割り当てる](assign-licenses.md)。
1. [アプリを展開する](deploy-apps.md)。
1. [デバイスをセットアップする](set-up-devices.md)
1. [Autopilot と登録ステータス ページの初回実行時エクスペリエンス](esp-first-run.md)のセットアップ。
1. [ユーザー サポート機能を有効にする](enable-support.md)。
1. [ユーザーがデバイスを使えるようにする](get-started-devices.md)。
1. [アプリ制御の使用を開始する](get-started-app-control.md)。
