---
title: Microsoft 365 for enterprise テスト環境に iOS/iPadOS と Android デバイスを登録する
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: このテストラボガイドを使用して、Microsoft 365 テスト環境にデバイスを登録し、リモートで管理します。
ms.openlocfilehash: 06f83d1ed61bcc530b6aa974d7730f1aadc0ecbd
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367085"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

この記事では、Microsoft 365 for enterprise テスト環境で iOS/iPadOS と Android デバイス用の基本的なモバイルデバイス管理機能を登録してテストする方法について説明します。

テスト環境で iOS/iPadOS と Android デバイスを登録するには、3つのフェーズが含まれます。
- [フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: iOS/iPadOS と Android デバイスを登録する](#phase-2-enroll-your-ios-and-android-devices)
- [フェーズ 3: iOS/iPadOS と Android デバイスをリモートで管理する](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件を持つ軽量な方法で iOS/iPadOS と Android デバイスを登録する場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズに iOS/iPadOS と Android デバイスを登録する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の指示に従ってください。
  
> [!NOTE]
> 自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動ライセンスおよびグループメンバーシップをテストできるようにするためのオプションとして提供されており、一般的な組織を表す環境で試してみることができます。

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>フェーズ 2: iOS および Android デバイスを登録する

デバイスを管理するためにモバイルデバイス管理 (MDM) ソリューションを検討している場合は、Microsoft Intune を使用できます。 Intune を含む MDM プロバイダーを使用している場合、デバイスは "登録済み" です。 登録すると、構成した機能と設定が表示されます。 

Intune では、iOS/iPadOS と Android デバイスを登録する方法がいくつかあります。 組織にとって最適な登録オプションを選択できます。 詳細とガイダンスについては、次の記事を参照してください。

- [展開ガイド: Microsoft Intune での iOS と iPadOS デバイスの登録](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [展開ガイド: Android デバイスを Microsoft Intune に登録する](/mem/intune/fundamentals/deployment-guide-enrollment-android)

Intune をデバイスの管理に使用する準備ができていて、何らかのガイダンスが必要な場合は、次の情報が役に立つことがあります。

- [デバイス管理の概要](/mem/intune/fundamentals/what-is-device-management)
- [チュートリアル: Microsoft エンドポイントマネージャーのチュートリアル Intune](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [展開ガイド: セットアップまたは Microsoft Intune への移動](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>フェーズ 3: iOS および Android デバイスをリモートで管理する

Microsoft Intune は、リモートロックとパスコードのリセット機能を提供します。 他のユーザーがデバイスを失った場合は、デバイスをリモートでロックすることができます。 他のユーザーがパスコードを忘れた場合は、リモートでリセットできます。

- IOS/iPadOS または Android デバイスをリモートでロックするには、「 [Intune でデバイスをリモートロック](/mem/intune/remote-actions/device-remote-lock)する」を参照してください。
- パスコードをリモートでリセットするには、「 [Intune でデバイスのパスコードをリセットまたは削除](/mem/intune/remote-actions/device-passcode-reset)する」を参照してください。

リモートで実行できるその他のタスクについては、「 [使用可能なデバイスの操作](/mem/intune/remote-actions/device-management#available-device-actions)」を参照してください。
    
## <a name="next-step"></a>次の手順

テスト環境での [モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 機能とその他の機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
  
[Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)
