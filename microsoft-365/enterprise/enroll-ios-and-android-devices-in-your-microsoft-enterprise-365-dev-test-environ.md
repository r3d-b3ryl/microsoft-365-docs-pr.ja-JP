---
title: iOS/iPadOS デバイスと Android デバイスをエンタープライズ テスト環境Microsoft 365に登録する
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: このテスト ラボ ガイドを使用して、デバイスをテスト環境に登録Microsoft 365リモートで管理します。
ms.openlocfilehash: 5e27f2eecc9edda0a0fe7225d4ed47c7431eee77
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/12/2021
ms.locfileid: "59189630"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境用に iOS Microsoft 365 Android デバイスを登録する

*このテスト ラボ ガイドは、エンタープライズ テスト環境Microsoft 365にのみ使用できます。*

この記事では、エンタープライズ テスト環境用に、iOS/iPadOS および Android デバイスの基本的なモバイル デバイス管理機能を登録およびテストするMicrosoft 365説明します。

テスト環境での iOS/iPadOS デバイスと Android デバイスの登録には、次の 3 つのフェーズがあります。
- [フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: iOS/iPadOS および Android デバイスを登録する](#phase-2-enroll-your-ios-and-android-devices)
- [フェーズ 3: iOS/iPadOS デバイスと Android デバイスをリモートで管理する](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックの Microsoft 365 内のすべての記事への視覚的なマップについては、「Microsoft 365 テスト ラボ ガイド スタック」[を参照してください](../downloads/Microsoft365EnterpriseTLGStack.pdf)。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境Microsoft 365を構築する

最小要件で iOS/iPadOS デバイスと Android デバイスを軽量な方法で登録する場合は、「Lightweight 基本構成」の手順 [に従います](lightweight-base-configuration-microsoft-365-enterprise.md)。
  
iOS/iPadOS デバイスと Android デバイスをシミュレートされたエンタープライズに登録する場合は、「パススルー認証」の手順 [に従います](pass-through-auth-m365-ent-test-environment.md)。
  
> [!NOTE]
> ライセンスとグループ の自動メンバーシップをテストするには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメイン サービス (AD DS) フォレストのディレクトリ同期を含む、シミュレートされたエンタープライズ テスト環境は必要とされません。 このオプションは、ライセンスとグループ の自動メンバーシップをテストし、一般的な組織を表す環境で試してみることができます。

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>フェーズ 2: iOS デバイスと Android デバイスを登録する

デバイスを管理するためのモバイル デバイス管理 (MDM) ソリューションを検討している場合は、モバイル デバイス管理Microsoft Intune。 Intune を含む MDM プロバイダーを操作する場合、デバイスは "登録" されます。 登録すると、構成した機能と設定が受け取されます。 

Intune では、iOS/iPadOS および Android デバイスを登録する方法がいくつかあります。 組織に最適な登録オプションを選択できます。 詳細とガイダンスについては、次の記事を参照してください。

- [展開ガイド: iOS デバイスと iPadOS デバイスをデバイスに登録Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [展開ガイド: Android デバイスをデバイスに登録Microsoft Intune](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Intune をデバイス管理に使用する準備が整い、ガイダンスが必要な場合は、次の情報が役立つ場合があります。

- [デバイス管理の概要](/mem/intune/fundamentals/what-is-device-management)
- [チュートリアル: チュートリアル Intune in Microsoft エンドポイント マネージャー](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [展開ガイド: セットアップまたは移行Microsoft Intune](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>フェーズ 3: iOS デバイスと Android デバイスをリモートで管理する

Microsoft Intune、リモート ロックとパスコードのリセット機能を提供します。 ユーザーがデバイスを紛失した場合は、リモートでデバイスをロックできます。 パスコードを忘れた場合は、リモートでリセットできます。

- iOS/iPadOS または Android デバイスをリモートでロックするには、「Intune でデバイスをリモートでロック [する」を参照してください](/mem/intune/remote-actions/device-remote-lock)。
- パスコードをリモートでリセットするには、「Intune でデバイス パスコードをリセット [または削除する」を参照してください](/mem/intune/remote-actions/device-passcode-reset)。

リモートで実行できるその他のタスクについては、「使用可能なデバイスアクション [」を参照してください](/mem/intune/remote-actions/device-management#available-device-actions)。
    
## <a name="next-step"></a>次の手順

テスト環境 [で、その他の](m365-enterprise-test-lab-guides.md#mobile-device-management) モバイル デバイス管理機能を確認します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
  
[エンタープライズ テスト環境Microsoft 365デバイス コンプライアンス ポリシー](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 for Enterprise の概要](microsoft-365-overview.md)
