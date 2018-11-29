---
title: Microsoft 365 Enterprise テスト環境の MAM のポリシー
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: Intune モバイル アプリケーション管理 (MAM) ポリシー Microsoft 365 エンタープライズ環境のテストを追加するのにには、このテスト ラボ ガイド 』 を使用します。
ms.openlocfilehash: f00379a5e70dce5e07c031a7647b27041d3fa9d1
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869628"
---
# <a name="mam-policies-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 Enterprise テスト環境の MAM のポリシー

この資料の手順については、Microsoft 365 エンタープライズ Intune モバイル アプリケーション管理 (MAM) ポリシーのテスト環境を追加します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。

最小要件で軽量な方法で MAM のポリシーを構成する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。
  
シミュレートされた企業で MAM のポリシーを構成する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。
  
> [!NOTE]
> ライセンス テストを自動化し、グループのメンバーシップには、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されている必要はありませんし、Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。 
>  

## <a name="phase-2-create-and-deploy-mam-policies-for-ios-and-android-devices"></a>フェーズ 2:iOS デバイスと Android デバイス用の MAM ポリシーを作成し展開する

このフェーズでは、2 つの異なる MAM ポリシー (1 つは iOS デバイス用、もう 1 つは Android デバイス用) を作成し展開します。
  
1. Office 365 ポータルに移動 ([https://portal.office.com](https://portal.office.com)) し、グローバル管理者アカウントを使用して、Office 365 の試用版サブスクリプションにサインインします。
    
2. 、お使いのブラウザーの新しいタブで開くには、Azure ポータル[https://portal.azure.com](https://portal.azure.com)。

3. [Azure ポータル] タブで、Internet Explorer のナビゲーション ウィンドウで**すべてのサービス**] をクリックし、入力**Intune**、 **Intune**] をクリックします。
    
4. **Microsoft Intune**ブレードで**まだデバイスの管理を有効にしていない**メッセージが表示されたらをクリックします。**モバイル デバイスの管理機関**のブレードでは、 **Intune MDM 機関**をクリックし、し、[**選択**] をクリックします。[ブラウザー] タブを更新します。
    
5. 左側のナビゲーション ウィンドウで、**[グループ]** をクリックします。
    
6. **グループのグループのすべての**ブレードでは、[ **+ 新しいグループ**をクリックします。
    
7. **グループ**・ ブレードの上の**Office 365**を選択**グループの種類ですか?** **iOS デバイスのユーザーの管理****名**、**メンバーシップの種類**、**割り当て**を選択して入力し、[**作成**] をクリックします。 
    
8. **[グループ]** ブレードを閉じます。
    
9. **グループのグループのすべての**ブレードでは、[**追加**] をクリックします。
    
10. **グループ**・ ブレードの上の**Office 365**を選択**グループの種類ですか?** **Android 管理デバイスのユーザー** **名**、**メンバーシップの種類**、**割り当て**を選択して入力し、[**作成**] をクリックします。
    
11. **グループのグループのすべての**ブレードを閉じます。
    
12. **[Intune]** ブレードの **[クイック タスク]** 一覧で、**[コンプライアンス ポリシーの作成]** をクリックします。
    
13. **[コンプライアンス ポリシー プロファイル]** ブレードで、**[ポリシーの作成]** をクリックします。
    
14. **[ポリシーの作成]** ブレードの **[名前]** で、「**iOS**」と入力します。**[プラットフォーム]** で **[iOS]** を選択し、**[iOS コンプライアンス ポリシー]** ブレードで **[OK]** をクリックし、次いで **[作成]** をクリックします。
    
15. **[コンプライアンス ポリシー プロファイル]** ブレードで、**[ポリシーの作成]** をクリックします。
    
16. **[ポリシーの作成]** ブレードの **[名前]** で、「**Android**」と入力します。**[プラットフォーム]** で **[Android]** を選択し、**[Android コンプライアンス ポリシー]** ブレードで **[OK]** をクリックし、次いで **[作成]** をクリックします。
    
17. **[コンプライアンス ポリシー プロファイル]** ブレードで、**Android** のポリシー名をクリックします。
    
18. **[Android - プロパティ]** ブレードの左側のナビゲーションで、**[割り当て]**、**[グループの選択]** の順にクリックします。
    
19. **[グループの選択]** ブレードで、**[管理された Android デバイス ユーザー]** グループをクリックし、**[選択]** をクリックします。
    
20. **保存**] をクリックして、**アプリの割り当て**のブレードを閉じます。
    
21. **[コンプライアンス ポリシー プロファイル]** ブレードで、**iOS** のポリシー名をクリックします。
    
22. **[iOS - プロパティ]** ブレードの左側のナビゲーションで、**[割り当て]**、**[グループの選択]** の順にクリックします。
    
23. **[グループの選択]** ブレードで、**[管理された iOS デバイス ユーザー]** グループをクリックし、**[選択]** をクリックします。
    
24. **保存**] をクリックし、 **iOS の割り当て**のブレードを閉じます。
    
25. **[コンプライアンス ポリシー プロファイル]** ブレードを閉じます。
    
26. **[Intune]** ブレードの左側のナビゲーションで、**[アプリの管理]** をクリックします。
    
27. **[モバイル アプリ]** ブレードで、**[アプリ]** をクリックします。
    
28. アプリの一覧で、**[PowerPoint]** をクリックします。  
    
29. **[PowerPoint の概要]** ブレードで、**[割り当て] > [グループの選択] > [iOS デバイスの管理] > [選択]** の順にクリックします。**[種類]** で、**[利用可能]** を選択して、**[保存]** をクリックします。
    
30. 次のアプリケーションには、29 の手順を繰り返します。
    
    - Outlook for Android
    
    - Word for iOS
    
    - Excel for iOS
    
    - iOS 版 Outlook
    
    - Microsoft Dynamics CRM on iPad for iOS
    
    - Microsoft Dynamics CRM on iPhone for iOS
    
    - 電話用 Dynamics CRM for Android
    
    - タブレット用 Dynamics CRM for Android
    
    - Excel for Android
    
    - Word for Android
    
    - OneNote for iOS
    
31. **[モバイル アプリ - アプリ]** ブレードを閉じます。
    
32. **[モバイル アプリ]** ブレードで、**[アプリ保護ポリシー]** をクリックします。
    
33. **[アプリ保護ポリシー]** ブレードで、**[ポリシーの追加]** をクリックします。
    
34. **[ポリシーの追加]** ブレードで、「**iOS**」と入力して、**[必要なアプリの選択]** をクリックします。
    
35. **[アプリ]** ブレードで、**[PowerPoint]**、**[Microsoft Dynamics CRM on iPhone]**、**[Excel]**、**[Microsoft Dynamics CRM on iPhone]**、**[Word]**、**[OneNote]**、**[Outlook]** をクリックし、**[選択]** をクリックします。
    
36. **[ポリシーの追加]** ブレードで、**[作成]** をクリックします。
    
37. **[アプリ保護ポリシー]** ブレードで、**[ポリシーの追加]** をクリックします。
    
38. **[ポリシーの追加]** ブレードで、「**Android**」と入力します。**[プラットフォーム]** で **[Android]** を選択して、**[必要なアプリの選択]** をクリックします。
    
39. **[アプリ]** ブレードで、**[PowerPoint]**、**[タブレット用 Dynamics CRM]**、**[Excel]**、**[Word]**、**[Outlook]**、**[電話用 Dynamics CRM]** をクリックし、**[選択]** をクリックします。
    
40. **[ポリシーの追加]** ブレードで、**[作成]** をクリックします。
    
これで、2 つの MAM ポリシー (1 つは iOS デバイス用、もう 1 つは Android デバイス用) が設定され、選択されたアプリの設定をテストする用意ができました。 
  
## <a name="next-step"></a>次の手順

[モバイル デバイスの管理](m365-enterprise-test-lab-guides.md#mobile-device-management)機能が追加し、テスト環境での機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 エンタープライズのテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)です。
  
[Microsoft 365 Enterprise テスト環境に iOS および Android デバイスを登録する](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
  
[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[エンタープライズ モビリティとセキュリティ (EMS)](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)
