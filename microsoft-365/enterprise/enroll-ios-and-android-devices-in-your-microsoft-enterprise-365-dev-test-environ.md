---
title: Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/11/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: Microsoft 365 テスト環境でデバイスを登録し、それらをリモートで管理するには、このテスト ラボ ガイド 』 を使用します。
ms.openlocfilehash: 98696104ee8453adb7449980cf439eeb152aeea9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869136"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する

によって、この資料に記載されている手順に従うことができます登録し、iOS および Android デバイス用の基本的なモバイル デバイス管理機能を Microsoft 365 エンタープライズ テスト環境でテストします。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。

最小要件で軽量な方法で iOS および Android のデバイスを登録する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。
  
シミュレートされた企業であっを登録する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。
  
> [!NOTE]
> ライセンス テストを自動化し、グループのメンバーシップには、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されている必要はありませんし、Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>フェーズ 2: iOS および Android デバイスを登録します。

指示を使用して、最初に、[をインストールし、会社のポータル アプリケーションにサインイン](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios)、テスト環境を Microsoft Intune 会社のポータル アプリケーションをカスタマイズするのには。

次に、手順を使用[、会社のリソースへのアクセス権を設定](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)iOS デバイスを登録します。

次に、手順を使用[Intune に Android デバイスの登録](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)Android のデバイスを登録します。

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>フェーズ 3: は、iOS および Android のデバイスをリモートで管理します。

Microsoft Intune では、リモート ロックとパスコードの両方のリセット機能を提供します。他のユーザーを失った場合、デバイス、デバイスをリモートでロックできます。パスコードを忘れてしまった人の場合リモートでリセットすることができます。
  
IOS または Android デバイスをリモートでロック。

1. Azure ポータルにサインインするのに[https://portal.azure.com](https://portal.azure.com)のグローバル管理者アカウントの資格情報を使用します。
2. **すべてのサービス**をクリックして、 **Intune**を入力し、 **Intune**] をクリックします。
3. クリックして**デバイス > のすべてのデバイス**。
4. デバイスの一覧で、iOS または Android デバイスをクリック**リモート ロック**の動作です。

    
パスコードをリモートからリセットするには、

1. 必要な場合がある Azure ポータルにサインイン[https://portal.azure.com](https://portal.azure.com)のグローバル管理者アカウントの資格情報を使用します。
2. **すべてのサービス**をクリックして、 **Intune**を入力し、 **Intune**] をクリックします。
3. クリックして**デバイス > のすべてのデバイス**。
4. デバイスの一覧から管理、iOS または Android デバイスをクリックして**を選択.詳細**。**パスコードを削除する**デバイスのリモート操作を選択します。

追加の実験を行うには、[利用可能なデバイスの操作](https://docs.microsoft.com/intune/device-management#available-device-actions)を参照してください。

    
## <a name="next-step"></a>次の手順

[モバイル デバイスの管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能が追加し、テスト環境での機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
  
[Microsoft 365 Enterprise テスト環境の MAM のポリシー](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[エンタープライズ モビリティとセキュリティ (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
