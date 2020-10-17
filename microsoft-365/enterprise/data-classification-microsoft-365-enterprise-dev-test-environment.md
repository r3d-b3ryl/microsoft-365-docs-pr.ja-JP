---
title: Microsoft 365 for enterprise テスト環境のデータ分類
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: このテストラボガイドを使用して、Microsoft 365 for enterprise テスト環境のドキュメントに対して保持ラベルを作成して使用します。
ms.openlocfilehash: 5cc77167db866d99f0beea5f554a777ecf355046
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487734"
---
# <a name="data-classification-for-your-microsoft-365-for-enterprise-test-environment"></a>Microsoft 365 for enterprise テスト環境のデータ分類

*このテストラボガイドは、Microsoft 365 for enterprise および Office 365 エンタープライズテスト環境の両方で使用できます。*

この記事では、エンタープライズテスト環境の Microsoft 365 で保持ラベルを使用してデータ分類を構成する方法について説明します。

テスト環境でデータを分類するには、3つのフェーズが必要です。
- [フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [フェーズ 2: 保持ラベルを作成する](#phase-2-create-retention-labels)
- [フェーズ 3: ドキュメントに保持ラベルを適用する](#phase-3-apply-retention-labels-to-documents)

![Microsoft クラウドのテスト ラボ ガイド](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> Microsoft 365 for enterprise のテストラボガイドスタックに含まれるすべての記事のビジュアルマップについては、「 [microsoft 365 for enterprise のテストラボガイドスタック](../downloads/Microsoft365EnterpriseTLGStack.pdf)」を参照してください。
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>フェーズ 1: Microsoft 365 for enterprise テスト環境を構築する

最小要件での軽量な方法で保持ラベルを構成する場合は、「 [軽量な基本構成](lightweight-base-configuration-microsoft-365-enterprise.md)」の手順に従ってください。
  
シミュレートされたエンタープライズで保持ラベルを構成する場合は、 [パススルー認証](pass-through-auth-m365-ent-test-environment.md)の手順に従います。
  
> [!NOTE]
> 保持ラベルをテストするには、シミュレートされたエンタープライズテスト環境を使用する必要はありません。これには、インターネットに接続されたシミュレートされたイントラネットと、Active Directory ドメインサービス (AD DS) フォレストのディレクトリ同期が含まれます。 この記事は、自動化されたライセンスとグループメンバーシップをテストし、一般的な組織を表す環境で試してみるためのオプションとして提供されています。

## <a name="phase-2-create-retention-labels"></a>フェーズ 2: 保持ラベルを作成する

このフェーズでは、SharePoint Online ドキュメントフォルダーのさまざまな保持レベルの保持ラベルを作成します。

1. グローバル管理者アカウントを使用して、 [Microsoft 365 セキュリティセンター](https://security.microsoft.com/homepage) にサインインします。
1. ブラウザーの [**ホーム-Microsoft 365 セキュリティ**] タブで、[**分類**  >  **保持ラベル**] を選択します。
1. [**ラベルを作成**] を選択します。
1. [**ラベルに名前**をつける] ウィンドウで、[**ラベルに名前**を付ける] に「 **Internal Public** 」と入力し、[**次へ**] を選択します。
1. **ファイルプラン記述子**ウィンドウで、[**次へ**] を選択します。
1. 必要に応じて、[ **ラベル設定** ] ウィンドウで、[ **保持** ] を **[オン**] に設定し、[ **次へ**] を選択します。
1. [ **設定の確認** ] ウィンドウで、[ **ラベルの作成**] を選択します。
1. 次の名前の追加ラベルについて、手順 3 から 7 を繰り返します。
  - プライベート
  - 機密
  - 非常に機密性の高い社外秘
1. [ **保持ラベル** ] ウィンドウで、[ **ラベルの発行**] を選択します。
1. [ **発行するラベルを選択** ] ウィンドウで、[ **発行するラベル**を選択] を選択します。
1. [ **ラベルの選択** ] ウィンドウで、[ **追加** ] を選択し、4つすべてのラベルを選択します。
1. [ **追加**] を選択し、[ **完了**] を選択します。
1. [ **発行するラベルを選択** ] ウィンドウで、[ **次へ**] を選択します。
1. [ **場所の選択** ] ウィンドウで、[ **次へ**] を選択します。
1. [**ポリシーに名前**をつける] ウィンドウで、[**名前**] に「 **Example organization** 」と入力し、[**次へ**] を選択します。
1. [ **設定の確認** ] ウィンドウで、[ **ラベルの発行**] を選択します。
 
保持ラベルが公開されるまでに数分かかる場合があります。

## <a name="phase-3-apply-retention-labels-to-documents"></a>フェーズ 3: ドキュメントに保持ラベルを適用する

このフェーズでは、SharePoint Online サイトの Documents フォルダー内のファイルの既定の保持ラベルの動作を検出し、ドキュメントの保持ラベルを手動で変更します。

最初に、機密レベルの SharePoint Online チームサイトを作成します。
  
1. ブラウザーのプライベートインスタンスを使用して、グローバル管理者アカウントを使用して [Microsoft 365 管理センター](https://admin.microsoft.com) にサインインします。
1. タイルの一覧で、[ **SharePoint**] を選択します。
1. ブラウザーの新しい [ **SharePoint** ] タブで、[ **サイトの作成**] を選択します。
1. **[サイトの作成]** ページで、**[チーム サイト]** を選択します。
1. [ **チームサイト名** ] ボックスに「 **SensitiveFiles**」と入力します。
1. [ **チームサイトの説明** ] ボックスに、「 **機密ファイル用の SharePoint サイト**」と入力します。
1. [ **プライバシー設定**] で、[ **プライベート-メンバーのみがこのサイトにアクセス可能**] を選択し、[ **次へ**] を選択します。
1. [ **誰を追加** しますか] ウィンドウで、[ **完了**] を選択します。
    
次に、機密保持ラベル用に SensitiveFiles チームサイトのドキュメントフォルダーを構成します。
  
1. ブラウザーの [ **SensitiveFiles** ] タブで、[ **ドキュメント**] を選択します。
1. [ **設定** ] アイコンを選択してから、[ **ライブラリの設定**] を選択します。
1. [ **権限と管理**] で、[ **このリストまたはライブラリ内のアイテムにラベルを適用する**] を選択します。 このオプションが表示されない場合、保持ラベルはまだ公開されていません。 後でこの手順を試してください。
1. [ **設定-ラベルの適用**] で、ドロップダウンボックスで [ **機密** ] を選択し、[ **保存**] を選択します。

次に、SensitiveFiles サイトで新しいドキュメントを作成し、そのアイテム保持ラベルを変更します。
    
1. Documents フォルダーで、[**新しい**  >  **Word 文書**] を選択します。
1. 空白のドキュメントに何らかのテキストを入力します。 テキストが保存されるまで待機します。
1. メニューバーで、[ **共有ドキュメント**] を選択します。
1. **Document.docx**ファイル名の横にある縦の省略記号を選択し、[**詳細**] を選択します。
1. 右ウィンドウの [ **プロパティ** ] セクションの [ **保持ラベルの適用**] で、ドキュメントに **機密** 保持ラベルが自動的に適用されている点に注意してください。
1. [**すべて編集**] をクリックします。
1. **Document.docx**ウィンドウで、[**保持ラベルの適用**] の下の [**高機密**] ラベルを選択し、[**保存**] を選択します。

## <a name="next-step"></a>次のステップ

テスト環境でのその他の [情報保護](m365-enterprise-test-lab-guides.md#information-protection) 機能と機能について説明します。

## <a name="see-also"></a>関連項目

[Microsoft 365 Enterprise のテスト ラボ ガイド](m365-enterprise-test-lab-guides.md)

[Microsoft 365 for enterprise の概要](microsoft-365-overview.md)

[エンタープライズドキュメントの Microsoft 365](https://docs.microsoft.com/microsoft-365-enterprise/)
