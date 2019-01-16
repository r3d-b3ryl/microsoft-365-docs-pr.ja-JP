---
title: Microsoft 365 企業のコンプライアンス ポリシーをデバイスのテスト環境
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Intune デバイス コンプライアンス ・ ポリシー、Microsoft 365 企業環境のテストを追加するのには、このテスト ラボ ガイド 』 を使用します。
ms.openlocfilehash: 1d957c5cdc888251224bbca43fe82ab0a15e7a93
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/16/2019
ms.locfileid: "26869628"
---
# <a name="device-compliance-policies-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企業のコンプライアンス ポリシーをデバイスのテスト環境

この資料の手順についてで Microsoft 365 エンタープライズ テスト環境に Intune デバイスのコンプライアンス ・ ポリシーを追加します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。

最小要件で軽量な方法で MAM のポリシーを構成する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。
  
シミュレートされた企業で MAM のポリシーを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。
  
> [!NOTE]
> ライセンス テストを自動化し、グループのメンバーシップには、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されている必要はありませんし、Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。 
>  

## <a name="phase-2-create-a-device-compliance-policy-for-windows-10-devices"></a>フェーズ 2: 10 の Windows のデバイスのデバイスのコンプライアンス ポリシーを作成します。

このフェーズでは、10 の Windows のデバイスのデバイスのコンプライアンス ポリシーを作成します。
  
1. Office のポータルに移動 ([https://office.com](https://office.com)) し、グローバル管理者アカウントを使用して、Office 365 の試用版サブスクリプションにサインインします。
    
2. 、お使いのブラウザーの新しいタブで開くには、Azure ポータル[https://portal.azure.com](https://portal.azure.com)。

3. ブラウザーのナビゲーション ウィンドウで [Azure ポータル] タブで**すべてのサービス**] をクリックし、入力**Intune**、 **Intune**] をクリックします。
    
4. **Microsoft Intune**ブレードで**まだデバイスの管理を有効にしていない**メッセージが表示されたらをクリックします。**モバイル デバイスの管理機関**のブレードでは、 **Intune MDM 機関**をクリックし、し、[**選択**] をクリックします。[ブラウザー] タブを更新します。
    
5. 左側のナビゲーション ウィンドウで、**[グループ]** をクリックします。
    
6. **グループのグループのすべての**ブレードでは、[ **+ 新しいグループ**をクリックします。
    
7. **グループ**・ ブレードの上の**Office 365**を選択**グループの種類ですか?** **Windows 10 の管理デバイスのユーザー** **名**、**メンバーシップの種類**、**割り当て**を選択して入力し、[**作成**] をクリックします。 
    
8. **[グループ]** ブレードを閉じます。
    
11. **グループのグループのすべての**ブレードを閉じます。
    
12. **クイック タスク**の一覧で、 **Microsoft Intune**ブレードでは、**コンプライアンス ・ ポリシーを作成する**をクリックします。
    
13. **[コンプライアンス ポリシー プロファイル]** ブレードで、**[ポリシーの作成]** をクリックします。
    
14. **ポリシーの作成**・ ブレードの**名前**、 **Windows 10**を入力します。**プラットフォーム**では、 **10 とそれ以降の Windows**を選択、 **Windows 10 コンプライアンス ・ ポリシー** ・ ブレードの上の [ **OK** ] をクリックでし、[**作成**] をクリックします。**Windows 10**ブレードを閉じます。
    
15. **コンプライアンス ・ ポリシーのプロファイル**のブレードでは、 **10 の Windows**ポリシーの名前をクリックします。
    
16. **Windows 10**ブレードは、**割り当て**をクリックし、**含めるグループを選択**] をクリックします。
    
17. **含めるグループを選択して**ブレードの**Windows 10 の管理デバイスのユーザー**グループをクリックし、**選択**] をクリックします。
    
18. **保存**] をクリックして、 **Windows の 10 の割り当て**のブレードを閉じます。
    
19. **[コンプライアンス ポリシー プロファイル]** ブレードを閉じます。
    
20. **Microsoft Intune**ブレードの左側のナビゲーションで [**クライアント アプリケーション**] をクリックします。
    
21. **クライアント アプリケーション**のブレードでは、**アプリケーション**をクリックし、し、[**追加**] をクリックします。 

22. **追加アプリケーション**のブレードでは、**アプリケーションの種類**を選択し、 **Office 365 製品ファミリ**では、 **Windows の 10**を選択し、します。

23. **アプリケーション スイートを構成する**をクリックし、[ **OK**] をクリックします。

24. **アプリケーション スイートの情報**をクリックして**Office アプリケーションの Windows 10** [**スイート名**]**スイートの説明**では、 **Office アプリケーションの Windows 10**と入力し、[ **OK**] をクリックします。

25. **アプリケーション スイートの設定**] をクリックし、**更新チャネル**では、**半年**を選択し、[ **OK**] をクリックします。

26. **追加のアプリケーション**のブレードでは、[**追加**を] をクリックします。

デバイス ・ コンプライアンス ・ ポリシーと**Windows 10**デバイスのコンプライアンス ・ ポリシーで選択したアプリケーションをテストするため、 **Windows 10 の管理デバイスのユーザー**グループのメンバーがあるようになりました。 
  
## <a name="next-step"></a>次の手順

[モバイル デバイスの管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能が追加し、テスト環境での機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 エンタープライズのテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)です。
  
[Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[エンタープライズ モビリティとセキュリティ (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
