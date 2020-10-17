---
title: Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する
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
ms.openlocfilehash: 3736934dbb62e84aad6a91fcd1d65b4a47ef8637
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487698"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

この記事では、Microsoft 365 for enterprise テスト環境に iOS および Android デバイス用の基本的なモバイルデバイス管理機能を登録およびテストする方法について説明します。

テスト環境に iOS および Android デバイスを登録するには、3つのフェーズが含まれます。
- [フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: iOS および Android デバイスを登録する](#phase-2-enroll-your-ios-and-android-devices)
- [フェーズ 3: iOS および Android デバイスをリモートで管理する](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件を持つ軽量な方法で iOS および Android デバイスを登録する場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズに iOS および Android デバイスを登録する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の指示に従ってください。
  
> [!NOTE]
> 自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動ライセンスおよびグループメンバーシップをテストできるようにするためのオプションとして提供されており、一般的な組織を表す環境で試してみることができます。

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>フェーズ 2: iOS および Android デバイスを登録する

最初に、インストールの手順を使用して、 [ポータルサイトアプリにサインイン](https://docs.microsoft.com/intune-user-help/install-and-sign-in-to-the-intune-company-portal-app-ios) し、テスト環境用の Microsoft Intune ポータルサイトアプリをカスタマイズします。

次に、「 [セットアップアクセス権を会社のリソースに](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) 登録する」の手順を使用して、iOS デバイスを登録します。

次に、「 [Intune に android デバイスを登録](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android) する」の手順を使用して android デバイスを登録します。

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>フェーズ 3: iOS および Android デバイスをリモートで管理する

Microsoft Intune には、リモート ロック機能とパスコードのリセット機能あります。 他のユーザーがデバイスを失った場合は、デバイスをリモートでロックすることができます。 他のユーザーがパスコードを忘れた場合は、リモートでリセットできます。
  
IOS または Android デバイスをリモートでロックするには、次の操作を行います。

1. [https://portal.azure.com](https://portal.azure.com)全体管理者アカウントの資格情報を使用して Azure portal にサインインします。
2. Azure portal で、検索ボックスに「 **intune** 」と入力し、[ **intune**] を選択します。
3. [ **デバイス > すべてのデバイス**] をクリックします。
4. デバイスの一覧で iOS または Android デバイスを選択し、[ **リモートロック** ] アクションを選択します。
    
パスコードをリモートでリセットするには

1. 必要に応じて、 [https://portal.azure.com](https://portal.azure.com) 全体管理者アカウントの資格情報を使用して Azure portal にサインインします。
2. Azure portal で、検索ボックスに「 **intune** 」と入力し、[ **intune**] を選択します。
3. [**デバイス**  >  **すべてのデバイス**] を選択します。
4. 管理するデバイスのリストから、iOS または Android デバイスを選択し、[...] を選択し**ます。その後、[****パスコード**デバイスのリモートアクションを削除する] を選択します。

その他の実験については、「 [使用可能なデバイスの操作](https://docs.microsoft.com/intune/device-management#available-device-actions)」を参照してください
    
## <a name="next-step"></a>次のステップ

テスト環境での [モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 機能とその他の機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
  
[Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)
