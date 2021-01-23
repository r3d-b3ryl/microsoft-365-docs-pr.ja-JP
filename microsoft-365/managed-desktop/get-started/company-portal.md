---
title: Intune ポータル サイトをデバイスにインストールする
description: Microsoft マネージド デスクトップ デバイスへのポータル サイト アプリのインストールに関する情報
keywords: Microsoft マネージド デスクトップ、Microsoft 365、ポータル サイト
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: bddf46e451408e4f17e58cc62186b7cd6cefb382
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939286"
---
# <a name="install-intune-company-portal-on-devices"></a>Intune ポータル サイトをデバイスにインストールする

Microsoft マネージド デスクトップでは、IT 管理者が Microsoft マネージド デスクトップ デバイスを使用してユーザー向け Intune ポータル サイトをインストールする必要があります。 組織にとっての利点を次に示します。
- ユーザーは、使用可能なアプリケーションを 1 か所で参照およびインストールできます。 
- IT 管理者は、ユーザーのカテゴリ別にアプリケーションを整理できます。  
- 一部のアプリケーション (Microsoft Project や Microsoft Visio など) では、Microsoft マネージド デスクトップを使用してポータル サイトを展開する必要があります。
- IT 管理者は、組織のポータル サイトをカスタマイズできます。 これには、ブランドイメージング、ローカル サポート連絡先の追加などです。 詳細については、「Microsoft Intune ポータル サイト アプリを構成する方法 [」を参照してください](https://docs.microsoft.com/intune/company-portal-app)。   

このトピックでは、Intune ポータル サイトを Microsoft マネージド デスクトップ ユーザーに展開するプロセスについて説明します。 全体的なプロセスは次のように表示されます。
1. ビジネス向け Microsoft Store からポータル サイトを購入し、Intune と同期する
2. ユーザーにポータル サイトを割り当てる
3. 変更をユーザーに伝える

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>手順 1 - ビジネス向け Microsoft Store からポータル サイトを購入し、Intune と同期する
アプリを購入して Intune と同期する方法については、「ビジネス向け [Microsoft Store](deploy-apps.md#msfb-apps) アプリ」の「アプリを Microsoft マネージド デスクトップ デバイスに展開する」 *を参照してください*。

このトピックでは、次の方法について説明します。 
- ビジネス向け Microsoft Store からポータル サイトを購入する 
- Intune とビジネス向け Microsoft Store の間で同期を強制する
- Intune とビジネス向け Microsoft Store の間のアクティブな同期を確認する 

## <a name="step-2---assign-company-portal-to-your-users"></a>手順 2 - ユーザーにポータル サイトを割り当てる
Microsoft マネージド デスクトップに登録すると、Microsoft マネージド デスクトップ操作によって、テナントにポータル サイトが自動的に展開され、組織内の Microsoft マネージド デスクトップ デバイスにアプリがインストールされます。

## <a name="step-3---communicate-change-to-your-users"></a>手順 3 - 変更をユーザーに伝える
組織の IT 管理者として、組織でポータル サイトを使用する方法をユーザーに知らせすることが重要です。 Microsoft マネージド デスクトップでは、次の方法をお勧めします。
- ポータル サイトからアプリケーションをインストールする手順。 詳しくは、デバイスへの [アプリのインストールと共有に関するページをご覧ください](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)。
- 現在利用できないアプリケーションの要求を IT 管理者に送信する方法。 詳細については、「アプリを [仕事や学校に依頼する」を参照してください](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft マネージド デスクトップの使用を開始する手順

1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)
2. [条件付きアクセスを調整する](conditional-access.md)
3. [ライセンスを割り当てる](assign-licenses.md)
4. Intune ポータル サイトを展開する (このトピック)
5. [Enterprise State Roaming を有効にする](enterprise-state-roaming.md)
6. [デバイスをセットアップする](set-up-devices.md)
7. [ユーザーがデバイスを使えるようにする](get-started-devices.md)
8. [アプリを展開する](deploy-apps.md)
