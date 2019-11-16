---
title: Microsoft 365 Enterprise テスト環境のデバイスコンプライアンスポリシー
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Intune デバイスコンプライアンスポリシーを Microsoft 365 Enterprise テスト環境に追加します。
ms.openlocfilehash: 6f37a898461ea67bc2927fcbac1a0f1b15adb036
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/15/2019
ms.locfileid: "38672563"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境のデバイスコンプライアンスポリシー

*このテストラボガイドは、Microsoft 365 エンタープライズテスト環境でのみ使用できます。*

この記事の手順に従って、Intune デバイスコンプライアンスポリシーを Microsoft 365 Enterprise テスト環境に追加します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 Enterprise のテスト環境を構築する

最低限の要件を使用して、柔軟な方法で MAM ポリシーを構成する場合は、「[軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで MAM ポリシーを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> 自動ライセンスおよびグループメンバーシップをテストするには、シミュレートされたエンタープライズテスト環境を必要としません。これには、インターネットに接続されたシミュレートされたイントラネットと Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみることができるオプションとして提供されています。 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>フェーズ 2: Windows 10 デバイスのデバイスコンプライアンスポリシーを作成する

このフェーズでは、Windows 10 デバイスのデバイスコンプライアンスポリシーを作成します。
  
1. Office 365 ポータル ([https://portal.office.com](https://portal.office.com)) に移動し、全体管理者アカウントを使用して office 365 テストラボサブスクリプションにサインインします。
    
2. ブラウザーの新しいタブで、Azure portal を開き[https://portal.azure.com](https://portal.azure.com)ます。

3. ブラウザーの [Azure portal] タブで、ナビゲーションウィンドウの [すべての**サービス**] をクリックし、「 **intune**」と入力して、[ **intune**] をクリックします。
    
4. **Microsoft Intune**ブレードで [**デバイス管理**] が有効になっていないことが表示された場合は、そのメッセージをクリックします。 [**モバイルデバイス管理機関**] ブレードで、[ **Intune MDM 機関**] をクリックし、[**選択**] をクリックします。 ブラウザーのタブを更新します。
    
5. 左側のナビゲーション ウィンドウで、**[グループ]** をクリックします。
    
6. [**グループ-すべてのグループ**] ブレードで、[ **+ 新しいグループ**] をクリックします。
    
7. **グループ**ブレードで、[ **Office 365** ] または [グループの種類に対して**セキュリティ**を**設定しますか?**] で、[管理された**Windows 10 デバイスのユーザー** **名**] を入力し、[**メンバーシップの種類**] で [**割り当て済み**] を選択し、[**作成**] をクリック 
    
8. **[グループ]** ブレードを閉じます。
    
11. [ **Groups-すべてのグループ**] ブレードを閉じます。
    
12. **Microsoft Intune**ブレードの [**クイックタスク**] リストで、[**コンプライアンスポリシーの作成**] をクリックします。
    
13. **[コンプライアンス ポリシー プロファイル]** ブレードで、**[ポリシーの作成]** をクリックします。
    
14. [**ポリシーの作成**] ブレードの [**名前**] で、「 **Windows 10**」と入力します。 [**プラットフォーム**] で、[ **windows 10 以降**] を選択し、 **windows 10 コンプライアンスポリシー**ブレードで [ **OK** ] をクリックして、[**作成**] をクリックします。 **Windows 10**ブレードを閉じます。
    
15. [**コンプライアンスポリシープロファイル**] ブレードで、 **Windows 10**のポリシー名をクリックします。
    
16. **Windows 10**ブレードで、[**割り当て**] をクリックし、[**含めるグループの選択**] をクリックします。
    
17. [ブレード**を含めるグループの選択**] で、[管理された**Windows 10 デバイスユーザー** ] グループをクリックし、[**選択**] をクリックします。
    
18. [**保存**] をクリックし、[ **Windows 10 割り当て**] ブレードを閉じます。
    
19. **[コンプライアンス ポリシー プロファイル]** ブレードを閉じます。
    
20. **Microsoft Intune**ブレードで、左側のナビゲーションの [**クライアントアプリ**] をクリックします。
    
21. **クライアントアプリ**ブレードで、[**アプリ**] をクリックし、[**追加**] をクリックします。 

22. [**アプリの追加**] ブレードで、[**アプリの種類**] を選択し、[ **Office 365 スイート**] の下の [ **Windows 10** ] を選択します。

23. [**アプリスイートの構成**] をクリックし、[ **OK**] をクリックします。

24. [**アプリスイートの情報**] をクリックし、[**スイート名**] に「 **windows 10 用 Office**アプリ」、「 **Suite Description**の**windows 10 用 Office アプリ**」と入力して、[ **OK**] をクリックします。

25. [**アプリスイートの設定**] をクリックし、 **[更新チャネル**の**半期**] を選択して、[ **OK]** をクリックします。

26. [**アプリの追加**] ブレードで、[**追加**] をクリックします。

これで、選択したアプリを**windows 10**デバイスコンプライアンスポリシーと、管理された**windows 10 デバイスユーザー**グループのメンバーに対してテストするためのデバイスコンプライアンスポリシーが作成されました。 グループの種類として Office 365 を選択すると、追加のリソースが作成されることに注意してください。 
  
## <a name="next-step"></a>次の手順

テスト環境での[モバイルデバイス管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能とその他の機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテストラボガイド](m365-enterprise-test-lab-guides.md)。
  
[Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Enterprise Mobility + Security (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
