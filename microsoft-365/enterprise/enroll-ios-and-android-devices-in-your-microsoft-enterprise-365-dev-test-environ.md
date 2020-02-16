---
title: Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: このテストラボガイドを使用して、Microsoft 365 テスト環境にデバイスを登録し、リモートで管理します。
ms.openlocfilehash: ae6ff9e704fc239638b5951a95ae23c45e85b7be
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067654"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する

*このテストラボ ガイドは、Microsoft 365 Enterprise テスト環境にのみ使用できます。*

この記事に記載されている手順に従って、Microsoft 365 エンタープライズテスト環境で iOS および Android デバイス用の基本的なモバイルデバイス管理機能を登録し、テストすることができます。

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> [ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する

最小要件を使用して iOS および Android デバイスを軽量な方法で登録する場合は、「軽量な[基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズに iOS および Android デバイスを登録する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の指示に従ってください。
  
> [!NOTE]
> 自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。 
>  

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>フェーズ 2: iOS および Android デバイスを登録する

最初に、インストールの手順を使用して、[ポータルサイトアプリにサインイン](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios)し、テスト環境用の Microsoft Intune ポータルサイトアプリをカスタマイズします。

次に、「[セットアップアクセス権を会社のリソースに](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios)登録する」の手順を使用して、iOS デバイスを登録します。

次に、「 [Intune に android デバイスを登録](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android)する」の手順を使用して android デバイスを登録します。

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>フェーズ 3: iOS および Android デバイスをリモートで管理する

Microsoft Intune には、リモート ロック機能とパスコードのリセット機能あります。 ユーザーがデバイスを紛失した場合は、デバイスをリモートからロックできます。 他のユーザーがパスコードを忘れた場合は、リモートでリセットできます。
  
IOS または Android デバイスをリモートでロックするには、次の操作を行います。

1. 全体管理者アカウントの資格情報[https://portal.azure.com](https://portal.azure.com)を使用して Azure portal にサインインします。
2. ブラウザーの [Azure ポータル] タブで、検索ボックスに「 **intune** 」と入力し、[ **intune**] をクリックします。
3. [**デバイス > すべてのデバイス**] をクリックします。
4. デバイスの一覧で、iOS または Android デバイスをクリックし、[**リモートロック**] アクションをクリックします。

    
パスコードをリモートからリセットするには、

1. 必要に応じて、全体管理者アカウントの[https://portal.azure.com](https://portal.azure.com)資格情報を使用して Azure portal にサインインします。
2. ブラウザーの [Azure ポータル] タブで、検索ボックスに「 **intune** 」と入力し、[ **intune**] をクリックします。
3. [**デバイス > すべてのデバイス**] をクリックします。
4. 管理するデバイスのリストから、iOS または Android デバイスをクリックし、[...] を選択し**ます。詳細を参照**してください。 次に、[**パスコード**デバイスのリモートアクションの削除] を選択します。

その他の実験については、「[使用可能なデバイスの操作](https://docs.microsoft.com/intune/device-management#available-device-actions)」を参照してください

    
## <a name="next-step"></a>次の手順

テスト環境での[モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能とその他の機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
  
[Microsoft 365 Enterprise テスト環境のデバイスコンプライアンスポリシー](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

