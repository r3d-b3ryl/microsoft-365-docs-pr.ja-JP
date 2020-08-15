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
ms.openlocfilehash: 3c77a7ea8ddc5120a2ce53fa0834dab213502657
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686756"
---
# <a name="device-compliance-policies-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 for enterprise テスト環境のデバイスコンプライアンスポリシー

*このテストラボガイドは、エンタープライズテスト環境の Microsoft 365 にのみ使用できます。*

この記事の手順を使用して、Windows 10 デバイスの場合は Intune デバイスコンプライアンスポリシーを、エンタープライズテスト環境には 365 Microsoft 365 Apps for enterprise に追加します。

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事へのビジュアル マップを確認してください。

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最低限の要件を使用して、柔軟な方法で MAM ポリシーを構成する場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> 自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する

このフェーズでは、Windows 10 デバイスのデバイスコンプライアンスポリシーを作成します。
  
1. [Microsoft 365 管理センター](https://admin.microsoft.com)に移動し、グローバル管理者アカウントを使用して microsoft 365 テストラボサブスクリプションにサインインします。
    
2. ブラウザーの新しいタブで、Azure portal を開き [https://portal.azure.com](https://portal.azure.com) ます。

3. ブラウザーの [Azure ポータル] タブで、検索ボックスに「 **intune** 」と入力し、[ **intune**] をクリックします。
    
4. [デバイス管理] が [ **現在有効になってい** ません] というメッセージが [ **Microsoft Intune** ] ウィンドウに表示される場合は、それをクリックします。 [ **モバイルデバイス管理機関** ] ウィンドウで、[ **Intune MDM authority**] をクリックし、[ **選択**] をクリックします。 ブラウザーのタブを更新します。
    
5. 左側のナビゲーション ウィンドウで、**[グループ]** をクリックします。
    
6. [ **グループ-すべてのグループ** ] ウィンドウで、[ **+ 新しいグループ**] をクリックします。
    
7. **グループ**ウィンドウで、[ **Microsoft 365** ] または [グループの種類に対して**セキュリティ**を**設定しますか?**] に「管理された**Windows 10 デバイスのユーザー** **名**」と入力し、[**メンバーシップの種類**で**割り当て済み**] を選択し、[**作成**] をクリックします。 
    
8. [ **Microsoft Intune**] をクリックします。 [ **Microsoft Intune** ] ウィンドウの [ **クイックタスク** ] リストで、[ **コンプライアンスポリシーの作成**] をクリックします。
    
9. [ **コンプライアンスポリシープロファイル** ] ウィンドウで、[ **ポリシーの作成**] をクリックします。
    
10. [ **ポリシーの作成** ] ウィンドウの [ **名前**] で、「 **Windows 10**」と入力します。 [**プラットフォーム**] で、[ **windows 10 以降**] を選択し、[ **windows 10 コンプライアンスポリシー** ] ウィンドウで [ **OK]** をクリックして、[**作成**] をクリックします。 
    
11. [ **コンプライアンスポリシープロファイル**] をクリックし、[ **Windows 10** ] ポリシー名をクリックします。
    
12. **Windows 10**ウィンドウで、[**割り当て**] をクリックし、[**含めるグループの選択**] をクリックします。
    
13. [ **含めるグループの選択** ] ウィンドウで、[管理された **Windows 10 デバイスユーザー** ] グループをクリックし、[ **選択**] をクリックします。
    
14. [ **保存**] をクリックし、[ **Microsoft Intune-概要**] をクリックして、左側のナビゲーションで [ **クライアントアプリ** ] をクリックします。
    
15. [ **クライアントアプリ** ] ウィンドウで、[ **アプリ**] をクリックし、[ **追加**] をクリックします。 

16. [**アプリの追加**] ウィンドウで、[**アプリの種類**] を選択し、 **Microsoft 365 スイート**の下の [ **Windows 10** ] を選択します。

17. [ **アプリの追加** ] ウィンドウで、[ **アプリスイートの情報**] を選択します。
 
18. [**アプリスイートの情報**] ウィンドウで、 **Suite 名**と**スイートの説明**の両方に「 **Microsoft 365 Apps for enterprise** 」と入力します。
[OK] をクリックします。

19. [ **アプリの追加** ] ウィンドウで、[ **アプリスイートの構成**] を選択し、[ **OK**] をクリックします。

20. [ **アプリの追加** ] ウィンドウで、[ **アプリスイートの設定**] を選択します。

21. [ **チャネルの更新**] で [ **半期エンタープライズ**] を選択し、[ **OK**] をクリックします。

22. [ **アプリの追加** ] ウィンドウで、[ **追加**] をクリックします。

これで、選択したアプリを **windows 10** デバイスコンプライアンスポリシーと、管理された **windows 10 デバイスユーザー** グループのメンバーに対してテストするためのデバイスコンプライアンスポリシーが作成されました。 Microsoft 365 をグループの種類として選択すると、追加のリソースが作成されることに注意してください。 
  
## <a name="next-step"></a>次の手順

テスト環境での [モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management) 機能とその他の機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 for enterprise のテストラボガイド](m365-enterprise-test-lab-guides.md)。
  
[Microsoft 365 のエンタープライズテスト環境に iOS および Android デバイスを登録する](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
