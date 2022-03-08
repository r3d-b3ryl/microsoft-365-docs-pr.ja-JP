---
title: デバイスIntune ポータル サイトインストールする
description: Microsoft Managed Desktop デバイスへのポータル サイト アプリのインストールに関する情報
keywords: Microsoft Managed Desktop、Microsoft 365、ポータル サイト
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: c7edc974bfd4a4f0d2d9611c80d0996aebc3ddb7
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63326868"
---
# <a name="install-intune-company-portal-on-devices"></a>デバイスIntune ポータル サイトインストールする

Microsoft Managed Desktop では、IT 管理者が Microsoft Managed Desktop デバイスを使用してIntune ポータル サイトユーザー用のアプリケーションをインストールする必要があります。 組織の利点は次のとおりです。

- ユーザーは、使用可能なアプリケーションを参照してインストールする場所を 1 つ持っています。
- IT 管理者は、ユーザーのカテゴリ別にアプリケーションを整理できます。  
- 一部のアプリケーション (Microsoft Project Microsoft Visioなど) では、Microsoft ポータル サイトデスクトップを使用して展開する必要があります。
- IT 管理者は、組織ポータル サイトをカスタマイズできます。 カスタマイズには、ブランドイメージング、ローカル サポート連絡先への追加などがあります。 詳細については、「How [to Configure the Microsoft Intune ポータル サイト App」を参照してください](/intune/company-portal-app)。

この記事では、Microsoft Managed Desktop ユーザーにIntune ポータル サイトを展開するプロセスについて説明します。 全体的なプロセスは次のように表示されます。

1. [Intune からポータル サイト購入ビジネス向け Microsoft Store Intune と同期します](#step-1-purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune)。
2. [ユーザーにポータル サイトを割り当てる](#step-2-assign-company-portal-to-your-users)。
3. [変更をユーザーに伝える。](#step-3-communicate-change-to-your-users)

## <a name="step-1-purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a>手順 1: Intune からポータル サイトをビジネス向け Microsoft Store Intune と同期する

アプリを購入して Intune と同期する方法については、「アプリを Microsoft [](deploy-apps.md#msfb-apps) Managed Desktop デバイスに展開する」の「ビジネス向け Microsoft Storeアプリ」*を参照してください*。

この記事では、次の方法について情報を提供します。

- 購入ポータル サイトからビジネス向け Microsoft Store。
- Intune とデバイス間の強制的な同期ビジネス向け Microsoft Store。
- Intune とデバイス間のアクティブな同期をビジネス向け Microsoft Store。

## <a name="step-2-assign-company-portal-to-your-users"></a>手順 2: ユーザーにポータル サイトを割り当てる

Microsoft Managed Desktop への登録後、テナントに ポータル サイトを自動的に展開し、組織の Microsoft Managed Desktop デバイスにアプリをインストールします。

## <a name="step-3-communicate-change-to-your-users"></a>手順 3: ユーザーに変更を伝える

組織の IT 管理者として、組織のユーザーに組織の管理者のポータル サイト知らせすることが重要です。 Microsoft Managed Desktop では、次の方法をお勧めします。

- アプリケーションをインストールする手順については、ポータル サイト。 詳細については、「デバイスにアプリ [をインストールして共有する」を参照してください](/intune-user-help/install-apps-cpapp-windows)。
- 現在利用できないアプリケーションの要求を IT 管理者に送信する方法。 詳細については、「アプリを [仕事または学校に依頼する」を参照してください](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft Managed Desktop の使用を開始する手順

1. [管理ポータル](access-admin-portal.md)にアクセスします。
1. [管理ポータルで管理者の連絡先を追加および確認する](add-admin-contacts.md)。
1. [登録後に設定を調整する](conditional-access.md)。
1. この記事では、Intune ポータル サイトを展開して割り当てる必要があります。
1. [ライセンスを割り当てる](assign-licenses.md)。
1. [アプリを展開する](deploy-apps.md)。
1. [デバイスの準備](prepare-devices.md)
1. [Autopilot と登録ステータス ページの初回実行時エクスペリエンス](esp-first-run.md)のセットアップ。
1. [ユーザー サポート機能を有効にする](enable-support.md)。
1. [ユーザーがデバイスを使えるようにする](get-started-devices.md)。
1. [アプリ制御の使用を開始する](get-started-app-control.md)。
