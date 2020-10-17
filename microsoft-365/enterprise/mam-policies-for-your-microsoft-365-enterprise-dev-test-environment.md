---
title: Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー
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
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Microsoft 365 for enterprise テスト環境に Intune デバイスコンプライアンスポリシーを追加します。
ms.openlocfilehash: c1de822e5a97416bd0c672d88f2902d8986638c8
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487414"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

この記事では、Windows 10 365 デバイスの Intune デバイスコンプライアンスポリシーを Microsoft 365 for enterprise テスト環境に追加する方法について説明します。

Intune デバイスコンプライアンスポリシーを追加するには、次の2つのフェーズが必要です。
- [フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する](#phase-2-create-a-device-compliance-policy-for-windows-10-devices)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件での軽量な方法で MAM ポリシーを構成する場合は、「 [簡易基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> 自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみるためのオプションとして提供されています。
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する

このフェーズでは、Windows 10 デバイスのデバイスコンプライアンスポリシーを作成します。
  
1. [Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、グローバル管理者アカウントを使用して microsoft 365 テストラボサブスクリプションにサインインします。
1. ブラウザーの新しいタブで、Azure portal を開き [https://portal.azure.com](https://portal.azure.com) ます。
1. Azure portal の検索ボックスに「 **intune**」と入力し、[ **intune**] を選択します。
1. [ **Microsoft Intune** ] ウィンドウに [**デバイス管理] がまだ有効になってい**ない場合は、そのメッセージを選択します。 [ **モバイルデバイス管理機関** ] ウィンドウで、[ **Intune MDM authority**] を選択し、[ **選択**] を選択します。
1. ブラウザーのタブを更新します。
1. 左側のナビゲーションウィンドウで、[ **グループ**] を選択します。
1. [ **グループ-すべてのグループ** ] ウィンドウで、[ **+ 新しいグループ**] を選択します。
1. **グループ**ウィンドウで、[ **Microsoft 365** ] または [**グループの種類**に対する**セキュリティ**] を選択し、[管理さ**れた** **Windows 10 デバイスのユーザー** **名**] を入力し、[**メンバーシップの種類**] で [割り当て済み] を選択して、[**作成**] を選択します。
1. [ **Microsoft Intune**] を選択します。
1. [ **Microsoft Intune** ] ウィンドウの [ **クイックタスク** ] リストで、[ **コンプライアンスポリシーの作成**] を選択します。
1. [ **コンプライアンスポリシープロファイル** ] ウィンドウで、[ **ポリシーの作成**] を選択します。
1. [ **ポリシーの作成** ] ウィンドウの [ **名前**] で、 **Windows 10**と入力します。 [**プラットフォーム**] で、[ **windows 10 以降**] を選択し、[ **windows 10 コンプライアンスポリシー** ] ウィンドウで [ **OK]** を選択して、[**作成**] を選択します。
1. [ **コンプライアンスポリシープロファイル**] を選択し、 **Windows 10** ポリシー名を選択します。
1. [ **Windows 10** ] ウィンドウで、[ **割り当て**] を選択し、[ **含めるグループの選択**] を選択します。
1. [ **含めるグループの選択** ] ウィンドウで、[管理された **Windows 10 デバイスユーザー** ] グループを選択し、[ **選択**] を選択します。
1. [ **保存**] を選択し、[ **Microsoft Intune-概要**] を選択してから、左側のナビゲーションで [ **クライアントアプリ** ] を選択します。
1. [ **クライアントアプリ** ] ウィンドウで、[ **アプリ**] を選択し、[ **追加**] を選択します。
1. [**アプリの追加**] ウィンドウで、[**アプリの種類**] を選択し、 **Microsoft 365 スイート**の下の [ **Windows 10** ] を選択します。
1. [ **アプリの追加** ] ウィンドウで、[ **アプリスイートの情報**] を選択します。
1. [**アプリスイートの情報**] ウィンドウで、 **Suite 名**と**スイートの説明**の両方に「**エンタープライズ向けの Microsoft 365 Apps** 」と入力し、[ **OK]** を選択します。
1. [ **アプリの追加** ] ウィンドウで、[ **アプリスイートの構成**] を選択し、[ **OK]** を選択します。
1. [ **アプリの追加** ] ウィンドウで、[ **アプリスイートの設定**] を選択します。
1. [ **チャネルの更新**] で、[ **半期エンタープライズ**] を選択し、[ **OK]** を選択します。
1. [ **アプリの追加** ] ウィンドウで、[ **追加**] を選択します。

これで、選択したアプリを **windows 10** デバイスコンプライアンスポリシーと、管理された **windows 10 デバイスユーザー** グループのメンバーに対してテストするためのデバイスコンプライアンスポリシーが作成されました。 **Microsoft 365**をグループの種類として選択すると、追加のリソースが作成されることに注意してください。
  
## <a name="next-step"></a>次のステップ

テスト環境での [モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 機能とその他の機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 for enterprise のテストラボガイド](m365-enterprise-test-lab-guides.md)。
  
[Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
