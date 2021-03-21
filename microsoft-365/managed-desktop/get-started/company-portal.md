---
title: Intune ポータル サイトをデバイスにインストールする
description: Microsoft Managed Desktop デバイスへのポータル サイト アプリのインストールに関する情報
keywords: Microsoft Managed Desktop, Microsoft 365, Company Portal
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f4c5d20529a210207e225d4a2b46d5935ae112c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925776"
---
# <a name="install-intune-company-portal-on-devices"></a>Intune ポータル サイトをデバイスにインストールする

Microsoft Managed Desktop では、IT 管理者が Microsoft 管理デスクトップ デバイスを使用してユーザーの Intune ポータルをインストールする必要があります。 組織の利点を次に示します。
- ユーザーは、使用可能なアプリケーションを参照してインストールする場所を 1 つ持っています。 
- IT 管理者は、ユーザーのカテゴリ別にアプリケーションを整理できます。  
- 一部のアプリケーション (Microsoft Project や Microsoft Visio など) では、Microsoft Managed Desktop を使用してポータル サイトを展開する必要があります。
- IT 管理者は、組織のポータル サイトをカスタマイズできます。 これには、ブランドイメージング、ローカル サポート連絡先の追加などです。 詳細については、「How to Configure the [Microsoft Intune Company Portal app」を参照してください](/intune/company-portal-app)。   

このトピックでは、Intune ポータル サイトを Microsoft Managed Desktop ユーザーに展開するプロセスについて説明します。 全体的なプロセスは次のように表示されます。
1. ビジネス向け Microsoft Store からポータル サイトを購入し、Intune と同期する
2. ユーザーにポータル サイトを割り当てる
3. 変更をユーザーに伝える

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>手順 1 - ビジネス向け Microsoft Store からポータル サイトを購入し、Intune と同期する
アプリを購入して Intune と同期する方法については、「Deploy apps to Microsoft Managed Desktop デバイス」の [「Microsoft Store for Business](deploy-apps.md#msfb-apps) アプリ」 *を参照してください*。

このトピックでは、次の方法について説明します。 
- ビジネス向け Microsoft Store からポータル サイトを購入する 
- Intune と Microsoft Store for Business の間で強制的に同期する
- Intune と Microsoft Store for Business の間のアクティブな同期を確認する 

## <a name="step-2---assign-company-portal-to-your-users"></a>手順 2 - ユーザーにポータル サイトを割り当てる
Microsoft Managed Desktop への登録後、Microsoft Managed Desktop Operations は自動的にポータル サイトをテナントに展開し、組織内の Microsoft Managed Desktop デバイスにアプリをインストールします。

## <a name="step-3---communicate-change-to-your-users"></a>手順 3 - ユーザーに変更を伝える
組織の IT 管理者として、組織でポータル サイトを使用する方法をユーザーに知らせすることが重要です。 Microsoft Managed Desktop では、次の方法をお勧めします。
- ポータル サイトからアプリケーションをインストールする手順。 詳細については、「デバイスにアプリ [をインストールして共有する」を参照してください](/intune-user-help/install-apps-cpapp-windows)。
- 現在利用できないアプリケーションの要求を IT 管理者に送信する方法。 詳細については、「アプリを [仕事または学校に依頼する」を参照してください](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop の使用を開始する手順

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)
2. [条件付きアクセスを調整する](conditional-access.md)
3. [ライセンスを割り当てる](assign-licenses.md)
4. Intune ポータル サイトの展開 (このトピック)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [デバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. [アプリを展開する](deploy-apps.md)