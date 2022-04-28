---
title: エンタープライズ テスト環境のMicrosoft 365に iOS/iPadOS および Android デバイスを登録する
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 11/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 49c7758a-1c01-4153-9b63-5eae3f6305ce
description: このテスト ラボ ガイドを使用して、Microsoft 365テスト環境にデバイスを登録し、それらをリモートで管理します。
ms.openlocfilehash: 5cefabf6b995754f6febe117776ad2de97443df0
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65092935"
---
# <a name="enroll-ios-and-android-devices-in-your-microsoft-365-for-enterprise-test-environment"></a>エンタープライズ テスト環境のMicrosoft 365に iOS デバイスと Android デバイスを登録する

*このテスト ラボ ガイドは、エンタープライズ テスト環境のMicrosoft 365にのみ使用できます。*

この記事では、エンタープライズ テスト環境のMicrosoft 365に iOS/iPadOS および Android デバイスの基本的なモバイル デバイス管理機能を登録してテストする方法について説明します。

テスト環境に iOS/iPadOS および Android デバイスを登録するには、次の 3 つのフェーズが含まれます。
- [フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: iOS/iPadOS および Android デバイスを登録する](#phase-2-enroll-your-ios-and-android-devices)
- [フェーズ 3: iOS/iPadOS および Android デバイスをリモートで管理する](#phase-3-manage-your-ios-and-android-devices-remotely)

![Microsoft クラウドのテスト ラボ ガイド。](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> エンタープライズ テスト ラボ ガイド スタックのMicrosoft 365のすべての記事へのビジュアル マップについては、エンタープライズ テスト ラボ ガイド [スタックのMicrosoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)に関するページを参照してください。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: エンタープライズ テスト環境のMicrosoft 365を構築する

最小要件を満たす軽量な方法で iOS/iPadOS および Android デバイスを登録する場合は、「 [Lightweight 基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従います。
  
シミュレートされたエンタープライズに iOS/iPadOS および Android デバイスを登録する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> 自動ライセンスとグループ メンバーシップのテストでは、シミュレートされたエンタープライズ テスト環境は必要ありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory Domain Services (AD DS) フォレストのディレクトリ同期が含まれます。 ここでは、自動ライセンスとグループ メンバーシップをテストし、一般的な組織を表す環境で実験できるように、オプションとして提供されています。

## <a name="phase-2-enroll-your-ios-and-android-devices"></a>フェーズ 2: iOS デバイスと Android デバイスを登録する

デバイスを管理するためのモバイル デバイス管理 (MDM) ソリューションを検討している場合は、Microsoft Intuneを使用できます。 Intuneを含む任意の MDM プロバイダーを操作する場合、デバイスは "登録" されます。 登録すると、構成した機能と設定が表示されます。 

Intuneでは、iOS/iPadOS および Android デバイスを登録する方法がいくつかあります。 組織に最適な登録オプションを選択できます。 詳細とガイダンスについては、次の記事を参照してください。

- [展開ガイド: Microsoft Intune で iOS および iPadOS デバイスを登録する](/mem/intune/fundamentals/deployment-guide-enrollment-ios-ipados)
- [展開ガイド: Microsoft Intune で Android デバイスを登録する](/mem/intune/fundamentals/deployment-guide-enrollment-android)

デバイス管理にIntuneを使用する準備ができていて、いくつかのガイダンスが必要な場合は、次の情報が役立つ場合があります。

- [デバイス管理の概要](/mem/intune/fundamentals/what-is-device-management)
- [チュートリアル: Microsoft エンドポイント マネージャーでの Intune のチュートリアル](/mem/intune/fundamentals/tutorial-walkthrough-endpoint-manager)
- [デプロイ ガイド: セットアップするか、Microsoft Intune に移動します](/mem/intune/fundamentals/deployment-guide-intune-setup)

## <a name="phase-3-manage-your-ios-and-android-devices-remotely"></a>フェーズ 3: iOS デバイスと Android デバイスをリモートで管理する

Microsoft Intuneは、リモート ロックとパスコードリセット機能を提供します。 誰かがデバイスを紛失した場合は、デバイスをリモートでロックできます。 誰かがパスコードを忘れた場合は、リモートでリセットできます。

- iOS/iPadOS または Android デバイスをリモートでロックするには、「[Intuneを使用してデバイスをリモートでロック](/mem/intune/remote-actions/device-remote-lock)する」を参照してください。
- パスコードをリモートでリセットするには、「[Intuneでデバイスパスコードをリセットまたは削除する](/mem/intune/remote-actions/device-passcode-reset)」を参照してください。

リモートで実行できるその他のタスクについては、 [使用可能なデバイス アクション](/mem/intune/remote-actions/device-management#available-device-actions)に関するページを参照してください。
    
## <a name="next-step"></a>次の手順

テスト環境で [追加のモバイル デバイス管理機能](m365-enterprise-test-lab-guides.md#mobile-device-management) と機能を確認します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)
  
[エンタープライズ テスト環境のMicrosoft 365のデバイス コンプライアンス ポリシー](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
  
[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)
