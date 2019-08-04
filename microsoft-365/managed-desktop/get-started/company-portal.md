---
title: Intune ポータルサイトの Microsoft 管理デスクトップデバイスをインストールする
description: Microsoft マネージドデスクトップデバイスへのポータルサイトアプリのインストールに関する情報
keywords: Microsoft マネージドデスクトップ、Microsoft 365、ポータルサイト
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/08/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: a9ce2b2455b6036170636ac564c450676473ac48
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390704"
---
# <a name="install-intune-company-portal-on-microsoft-managed-desktop-devices"></a>Microsoft マネージドデスクトップデバイスに Intune Company Portal をインストールする

Microsoft マネージドデスクトップでは、IT 管理者が Microsoft マネージドデスクトップデバイスを使用してユーザーに Intune ポータルサイトをインストールする必要があります。 組織にとって次のような利点があります。
- ユーザーは、利用可能なアプリケーションを参照してインストールする場所が1つあります。 
- IT 管理者は、ユーザーのカテゴリ別にアプリケーションを編成できます。  
- Microsoft Project や Microsoft Visio などの一部のアプリケーションでは、Microsoft マネージドデスクトップを使用して、会社のポータルを展開する必要があります。
- IT 管理者は、組織のためにポータルサイトをカスタマイズできます。 これには、ブランドイメージング、ローカルサポート連絡先での追加などが含まれます。 詳細については、「 [Microsoft Intune ポータルサイトアプリを構成する方法](https://docs.microsoft.com/intune/company-portal-app)」を参照してください。   

このトピックでは、Intune Company Portal を Microsoft Managed Desktop ユーザーに展開するプロセスについて説明します。 全体的なプロセスは次のようになります。
1. ビジネス向け Microsoft Store からの会社ポータルの購入と Intune との同期
2. ユーザーへの会社ポータルの割り当て
3. ユーザーに対する変更を連絡する

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>手順 1-ビジネス向け Microsoft Store から会社のポータルを購入し、Intune と同期する
アプリを購入して Intune と同期する方法の詳細については、「microsoft [Store For Business apps](deploy-apps.md#msfb-apps) In *microsoft Managed Desktop devices*」を参照してください。

このトピックでは、次の方法に関する情報を提供します。 
- ビジネス向け Microsoft Store からの会社ポータルの購入 
- ビジネス向けの Intune と Microsoft Store の同期を強制する
- ビジネス向けの Intune と Microsoft Store 間のアクティブな同期を確認する 

## <a name="step-2---assign-company-portal-to-your-users"></a>手順 2-ユーザーに会社のポータルを割り当てる
Microsoft マネージドデスクトップ管理ポータルを使用して、Microsoft マネージドデスクトップ操作に対するサポート要求を送信します。 サポート要求で、ユーザーに割り当てられている会社のポータルを要求します。 Microsoft マネージドデスクトップは、会社のポータルをテナントに展開し、組織内の Microsoft マネージドデスクトップデバイスにアプリをインストールします。

Microsoft マネージドデスクトップでのサポート要求の送信の詳細については、「 [Microsoft マネージドデスクトップの管理者サポート](../working-with-managed-desktop/admin-support.md)」を参照してください。

## <a name="step-3---communicate-change-to-your-users"></a>手順 3-ユーザーに変更を伝達する
組織の IT 管理者として、組織内の会社のポータルの使用方法をユーザーに知らせることが重要です。 Microsoft マネージドデスクトップの推奨事項:
- 会社のポータルからアプリケーションをインストールする手順について説明します。 詳細については、「[デバイスにアプリをインストールして共有](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)する」を参照してください。
- 現在利用できないアプリケーションについて、IT 管理者に要求を送信する方法。
