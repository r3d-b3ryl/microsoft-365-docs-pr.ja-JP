---
title: Microsoft 365 企業のデータのクラス分けのテスト環境
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
description: ガイドを使用してこのテスト ラボを作成し、Microsoft 365 エンタープライズ テスト環境でドキュメントを Office 365 のラベルを使用します。
ms.openlocfilehash: 718cf038d88f1431ec6ca6fce1554d4f44dc1cb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869613"
---
# <a name="data-classification-for-your-microsoft-365-enterprise-test-environment"></a>Microsoft 365 企業のデータのクラス分けのテスト環境

この資料の手順についてで Microsoft 365 エンタープライズ テスト環境で Office 365 のラベルを使用してデータのクラス分けを構成します。

![Microsoft クラウドのテスト ラボ ガイド](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> [ここ](https://aka.ms/m365etlgstack)をクリックして、Microsoft 365 Enterprise のテスト ラボ ガイド スタックに含まれるすべての記事のビジュアル マップを確認してください。
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>フェーズ 1: マイクロソフト 365 エンタープライズ テスト環境を構築します。

最小要件で軽量な方法で Office 365 のラベルを設定する場合は、[軽量の基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)に指示します。
  
シミュレートされた企業で Office 365 のラベルを設定する場合は、[パススルー認証](pass-through-auth-m365-ent-test-environment.md)に指示します。
  
> [!NOTE]
> Office 365 のラベルのテストは、シミュレートされたエンタープライズ テスト環境には、シミュレートされたイントラネットをインターネットに接続されていると Windows サーバーの AD フォレストの場合、ディレクトリ同期します。自動化されたライセンスとグループのメンバーシップをテストし、一般的な組織を表す環境で実験するためのオプションとしてここで。 

## <a name="phase-2-create-office-365-labels"></a>フェーズ 2: Office 365 のラベルを作成する

このフェーズでは、SharePoint Online のドキュメント フォルダーのセキュリティのさまざまなレベルのラベルを作成します。
  
1. 必要な場合プライベート インターネット ブラウザーのインスタンスを使用し、グローバル管理者アカウントを使用して Office 365 ポータルにサインインします。ヘルプについては、 [Office 365 にサインインするための場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)を参照してください。
    
2. **[Microsoft Office Home]** タブで、**[管理者]** タイルをクリックします。
    
3. ブラウザーの新しい **[Office 管理者センター]** タブで、**[管理センター] > [セキュリティとコンプライアンス]** をクリックします。
    
4. ブラウザーの新しい **[ホーム – セキュリティとコンプライアンス]** タブをクリックして、**[分類] > [ラベル]** をクリックします。
    
5. **[ホーム] > [ラベル]** ウィンドウで、 **[ラベルの作成]** をクリックします。
    
6. **[ラベルに名前をつける]** ウィンドウで、「 **内部パブリック**」と入力してから、 **[次へ]** をクリックします。
    
7. **[ラベル設定]** ウィンドウで、 **[次へ]** をクリックします。
    
8. **[設定の確認]** ウィンドウで、 **[このラベルを作成する]** をクリックしてから **[閉じる]** をクリックします。
    
9. 次の追加ラベルについて手順 5 から 8 を繰り返します。
    
  - Kirkland
    
  - 機密
    
  - 非常に機密性の高い社外秘
    
10. **[ホーム]、[ラベル]** ウィンドウで、**[Publish labels]\(ラベルの発行\)** をクリックします。
    
11. **[発行するラベルを選択]** ウィンドウで、 **[発行するラベルを選択]** をクリックします。
    
12. **[Choose labels]\(ラベルの選択\)** ウィンドウで、**[追加]** をクリックして 4 つのラベルをすべて選択します。
    
13. [ **完了**] をクリックします。
    
14. **[発行するラベルを選択]** ウィンドウで、 **[次へ]** をクリックします。
    
15. **[場所の選択]** ウィンドウで、 **[次へ]** をクリックします。
    
16. **[ポリシーに名前をつける]** ウィンドウで、 **[名前]** に「 **サンプル組織**」と入力してから、 **[次へ]** をクリックします。
    
17. **[設定の確認]** ウィンドウで、 **[ラベルの発行]** をクリックしてから **[閉じる]** をクリックします。

メモを公開するのには、ラベルには数分をかかる場合があります。

## <a name="phase-3-apply-office-365-labels-to-documents"></a>フェーズ 3: Office 365 のラベルをドキュメントに適用します。

このフェーズでは、SharePoint Online サイトの [ドキュメント] フォルダー内のファイルの既定のラベルの動作を検出し、ドキュメントのラベルを手動で変更します。

最初に、機密レベルの SharePoint Online チーム サイトを作成します。
  
1. ローカル コンピューターのブラウザーを使用し、全体管理者アカウントで Office 365 ポータルにサインインします。ヘルプについては、「[一般法人向け Office 365 にサインインする場所](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)」を参照してください。
    
2. タイルのリストで、 **[SharePoint]** をクリックします。
    
3. お使いのブラウザーで新しい**SharePoint** ] タブ、[**サイトを作成**] をクリックします。
    
4. **[サイトの作成]** ページで、 **[チーム サイト]** をクリックします。
    
5. **チームのサイト名**、 **SensitiveFiles**を入力します。
    
6. **チーム サイトの説明**] には、**機密性の高いファイルを SharePoint サイト**を入力します。
    
7.  **[プライバシー設定]** で、 **[プライベート - メンバーのみがこのサイトにアクセス可能**」を選択して **[次へ]** をクリックします。
    
8. **[誰を追加しますか]** ウィンドウで、 **[完了]** をクリックします。
    
次に、機密性の高いラベルの SensitiveFiles のチーム サイトの [ドキュメント] フォルダーを構成します。
  
1. お使いのブラウザーの [ **SensitiveFiles** ] タブで [**ドキュメント**] をクリックします。
    
2. 設定アイコンをクリックし、**[ライブラリの設定]** をクリックします。
    
3. **[権限と管理]** をクリックして、**[このライブラリ内の項目にラベルを適用]** をクリックします。
    
4. **ラベルの設定の適用**] で、ドロップ ダウン ボックスで、**重要な**選択し、し、[**保存**] をクリックします。

次に、SensitiveFiles サイトに新しいドキュメントを作成し、そのラベルを変更します。
    
1. [ドキュメント] フォルダーをクリックして**新規 > Word 文書**。
    
2. 白紙の文書でテキストを入力します。テキストを保存するを待ちます。
    
3. メニュー バーの [**共有ドキュメント**] をクリックします。
    
4. **Document.docx**ファイル名の横にある Word のアイコンをクリックします。
    
5. [**プロパティ**] セクションの [**ラベルの適用**] の右側のペインでドキュメントが自動的に適用される**機密**ラベルにあったことを確認します。
    
6. **すべてを編集**] をクリックします。
    
7. **Document.docx**ウィンドウで、[**ラベルの適用**] は、**機密度の高い**ラベルを選択し、し、[**保存**] をクリックします。

情報と実稼働環境で Office 365 のラベルへのリンクの**情報の保護**の段階では、[環境内の分類を構成する](data-classification-microsoft-365-enterprise-dev-test-environment.md)手順を参照してください。

## <a name="next-step"></a>次の手順

追加[情報の保護](m365-enterprise-test-lab-guides.md#information-protection)機能と、テスト環境での機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise を展開する](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise のドキュメントとリソース](https://docs.microsoft.com/microsoft-365-enterprise/)

 