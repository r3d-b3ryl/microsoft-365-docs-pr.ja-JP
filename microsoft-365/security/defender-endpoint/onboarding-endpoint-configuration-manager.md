---
title: Microsoft Endpoint Configuration Manager を使用したオンボーディング
description: Microsoft Endpoint Configuration Manager を使用して Microsoft Defender for Endpoint にオンボードする方法について説明します。
keywords: オンボーディング、構成、展開、展開、エンドポイント構成マネージャー、Microsoft Defender for Endpoint、コレクション作成、エンドポイント検出応答、次世代保護、攻撃表面の縮小、Microsoft エンドポイント構成マネージャー
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 84273ce3e060eb86ee246a5cc6a8cae3cba743b5
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934491"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager を使用したオンボーディング

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


この記事は展開ガイドの一部であり、オンボーディング方法の例として機能します。 

「計画 [」トピック](deployment-strategy.md) では、デバイスをサービスにオンボードする方法がいくつか用意されています。 このトピックでは、共同管理アーキテクチャについて説明します。 

![クラウドネイティブ アーキテクチャのイメージ ](images/co-management-architecture.png)
 *環境アーキテクチャの図*


Defender for Endpoint はさまざまなエンドポイントとツールのオンボーディングをサポートしますが、この記事ではそれらをカバーしません。 サポートされている他の展開ツールと方法を使用した一般的なオンボーディングの詳細については、「オンボードの概要 [」を参照してください](onboarding.md)。



このトピックでは、次のユーザーをガイドします。
- 手順 1: Windows デバイスをサービスにオンボーディングする 
- 手順 2: Defender for Endpoint の機能を構成する

このオンボーディング ガイダンスでは、Microsoft Endpoint Configuration Manager を使用する場合に実行する必要がある次の基本的な手順について説明します。
- **Microsoft Endpoint Configuration Manager でのコレクションの作成**
- **Microsoft Endpoint Configuration Manager を使用した Microsoft Defender for Endpoint の機能の構成**

>[!NOTE]
>この展開例では、Windows デバイスのみについて説明します。 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a>手順 1: Microsoft Endpoint Configuration Manager を使用して Windows デバイスをオンボードする

### <a name="collection-creation"></a>コレクションの作成
Microsoft Endpoint Configuration Manager を使用して Windows 10 デバイスをオンボードするには、展開で既存のコレクションをターゲットにするか、テスト用に新しいコレクションを作成できます。 

グループ ポリシーや手動メソッドなどのツールを使用したオンボーディングでは、システムにエージェントはインストールされない。 

Microsoft Endpoint Configuration Manager コンソール内では、オンボーディング プロセスがコンソール内のコンプライアンス設定の一部として構成されます。

この必要な構成を受け取るシステムは、Configuration Manager クライアントが管理ポイントからこのポリシーを受け取り続ける限り、その構成を維持します。 

Microsoft Endpoint Configuration Manager を使用してエンドポイントをオンボードするには、以下の手順に従います。

1. Microsoft Endpoint Configuration Manager コンソールで、[アセット] と [コンプライアンス **の概要] \> デバイス コレクション \> に移動します**。            

    ![Microsoft Endpoint Configuration Manager ウィザード 1 のイメージ](images/configmgr-device-collections.png)

2. [デバイス コレクション] **を右クリックし** 、[デバイス コレクション **の作成] を選択します**。

    ![Microsoft Endpoint Configuration Manager ウィザード 2 のイメージ](images/configmgr-create-device-collection.png)

3. [名前]**と [制限****コレクション] を指定し、[** 次へ] を **選択します**。

    ![Microsoft Endpoint Configuration Manager ウィザード 3 のイメージ](images/configmgr-limiting-collection.png)

4. [ルール **の追加] を選択** し、[ **クエリ ルール] を選択します**。

    ![Microsoft Endpoint Configuration Manager ウィザード 4 のイメージ](images/configmgr-query-rule.png)

5.  [直接 **メンバーシップ ウィザード** ] で **[次へ] をクリックし** 、[クエリ ステートメントの **編集] をクリックします**。

     ![Microsoft Endpoint Configuration Manager ウィザードのイメージ 5](images/configmgr-direct-membership.png)

6. [ **条件] を** 選択し、星のアイコンを選択します。

     ![Microsoft Endpoint Configuration Manager ウィザード 6 のイメージ](images/configmgr-criteria.png)

7. 条件の種類を **単純な** 値として保持し、オペレーティング システム **-** ビルド番号 、演算子の値が **14393** 以上の場合は、OK をクリックする場所を選択 **します**。

    ![Microsoft Endpoint Configuration Manager ウィザード 7 のイメージ](images/configmgr-simple-value.png)

8. [次 **へ] と [** 閉じる] **を選択します**。

    ![Microsoft Endpoint Configuration Manager ウィザード 8 のイメージ](images/configmgr-membership-rules.png)

9. **[次へ]** を選択します。

    ![Microsoft Endpoint Configuration Manager ウィザードのイメージ 9](images/configmgr-confirm.png)


このタスクを完了すると、環境内のすべての Windows 10 エンドポイントを持つデバイス コレクションが作成されます。 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a>手順 2: Microsoft Defender for Endpoint の機能を構成する 
このセクションでは、Windows デバイスで Microsoft Endpoint Configuration Manager を使用して次の機能を構成する方法について説明します。

- [**エンドポイントでの検出と対応**](#endpoint-detection-and-response)
- [**次世代の保護**](#next-generation-protection)
- [**攻撃面の減少**](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a>エンドポイントの検出および応答
#### <a name="windows-10"></a>Windows 10
Microsoft Defender セキュリティ センター内から、System Center Configuration Manager でポリシーを作成し、そのポリシーを Windows 10 デバイスに展開するために使用できる '.onboarding' ポリシーをダウンロードできます。

1. Microsoft Defender セキュリティ センター ポータルで、[設定] を選択 [し、[オンボーディング] を選択します](https://securitycenter.windows.com/preferences2/onboarding)。



2. [展開方法] で、サポートされている **バージョンの Microsoft Endpoint Configuration Manager を選択します**。

    ![Microsoft Defender for Endpoint オンボーディング ウィザード 10 のイメージ](images/mdatp-onboarding-wizard.png)

3. [パッケージ **のダウンロード] を選択します**。

    ![Microsoft Defender for Endpoint オンボーディング ウィザードのイメージ11](images/mdatp-download-package.png)

4. パッケージをアクセス可能な場所に保存します。
5. Microsoft Endpoint Configuration Manager で、[アセットとコンプライアンス] に移動し、[>の概要> Microsoft Defender ATP ポリシー> **に移動します**。

6. [Microsoft **Defender ATP ポリシー] を右クリックし、[Microsoft** Defender ATP ポリシー **の作成] を選択します**。

    ![Microsoft Endpoint Configuration Manager ウィザード 12 のイメージ](images/configmgr-create-policy.png)

7. 名前と説明を入力し、[ **オン** ボーディング] が選択されている場合は、[次へ] を選択 **します**。

    ![Microsoft Endpoint Configuration Manager ウィザード 13 のイメージ](images/configmgr-policy-name.png)


8. [ **参照**] をクリックします。

9. 上記の手順 4 からダウンロードしたファイルの場所に移動します。

10. [ **次へ**] をクリックします。
11. 適切なサンプル (None または All ファイルの種類)**を使用****してエージェントを構成します**。

    ![構成設定のイメージ1](images/configmgr-config-settings.png)

12. 適切な利用統計情報 (標準または **迅速) を****選択し**、[次へ] を **クリックします**。

    ![構成設定のイメージ2](images/configmgr-telemetry.png)

14. 構成を確認し、[次へ] を **クリックします**。

     ![構成設定のイメージ 3](images/configmgr-verify-configuration.png)

15. ウィザードが **完了したら** 、[閉じる] をクリックします。

16.  Microsoft Endpoint Configuration Manager コンソールで、作成した Defender for Endpoint ポリシーを右クリックし、[展開] を **選択します**。

     ![構成設定のイメージ 4](images/configmgr-deploy.png)

17. 右側のパネルで、前に作成したコレクションを選択し **、[OK] をクリックします**。

    ![構成設定のイメージ5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a>以前のバージョンの Windows クライアント (Windows 7 および Windows 8.1)
以前のバージョンの Windows のオンボーディングに必要な Defender for Endpoint Workspace ID と Workspace Key を識別するには、以下の手順に従います。

1. Microsoft Defender セキュリティ センター ポータルで、[オンボーディング **の設定] >選択します**。

2. [オペレーティング システム] で、[Windows 7 SP1 **8.1] を選択します**。

3. ワークスペース **ID とワークスペース キー****をコピーして** 保存します。 これらは、プロセスの後半で使用されます。

    ![オンボーディングのイメージ](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. Microsoft 監視エージェント (MMA) をインストールします。 <br>
    MMA は現在 (2019 年 1 月現在) 次の Windows オペレーティング システムでサポートされています。

    -   サーバー SKU: Windows Server 2008 SP1 以降

    -   クライアント SKU: Windows 7 SP1以降

    MMA エージェントを Windows デバイスにインストールする必要があります。 エージェントをインストールするには、MMA を使用してデータ[](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry)を収集するために、一部のシステムでカスタマー エクスペリエンスと診断テレメトリの更新プログラムをダウンロードする必要があります。 これらのシステム バージョンには、次のものが含まれますが、これらに限定されない場合があります。

    -   Windows 8.1

    -   Windows 7

    -   Windows Server 2016

    -   Windows Server 2012 R2

    -   Windows Server 2008 R2

    具体的には、次Windows 7 SP1パッチをインストールする必要があります。

    -   [KB4074598 のインストール](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)

    -   [4.5 .NET Framework以降](https://www.microsoft.com/download/details.aspx?id=30653)**)** または 
         [KB3154518 のいずれかをインストールします](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)。
        両方を同じシステムにインストールしない。

5. プロキシを使用してインターネットに接続する場合は、「プロキシ設定の構成」セクションを参照してください。

完了すると、1 時間以内にポータルにオンボード エンドポイントが表示されます。

### <a name="next-generation-protection"></a>次世代の保護 
Windows Defender ウイルス対策は、デスクトップ、ポータブル コンピューター、サーバーを対象に次世代の保護機能を提供する、組み込みのマルウェア対策ソリューションです。

1. Microsoft Endpoint Configuration Manager コンソールで、[アセットとコンプライアンスの概要 エンドポイント保護マルウェア対策ポリシー] に移動し、[マルウェア対策ポリシーの作成]**を選択します**。 **\> \> \>**

    ![マルウェア対策ポリシーのイメージ](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. [**スケジュールされたスキャン****]、[** スキャン設定]、[既定のアクション]、[リアルタイム保護]、[除外設定]、[詳細設定]、[脅威の上書き]、**クラウド保護サービス** とセキュリティ インテリジェンスの更新を選択し **、[OK] を選択します**。   

    ![次世代保護ウィンドウのイメージ 1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    特定の業界または一部の企業のお客様は、ウイルス対策の構成方法に関する特定のニーズを持っている場合があります。

  
    [クイック スキャンとフル スキャン、およびカスタム スキャン](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    詳細については [、「Windows Security 構成フレームワーク」を参照してください。](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)
  
    ![次世代保護ウィンドウ 2 のイメージ](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![次世代保護ウィンドウのイメージ 3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![次世代保護ウィンドウのイメージ 4](images/a28afc02c1940d5220b233640364970c.png)

    ![次世代保護ウィンドウのイメージ 5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![次世代保護ウィンドウのイメージ 6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![次世代保護ウィンドウのイメージ 7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![次世代保護ウィンドウ 8 のイメージ](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![次世代保護ウィンドウのイメージ 9](images/3876ca687391bfc0ce215d221c683970.png)

3. 新しく作成したマルウェア対策ポリシーを右クリックし、[展開] を **選択します**。

    ![次世代保護ウィンドウ 10 のイメージ](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. 新しいマルウェア対策ポリシーを Windows 10 コレクションにターゲットに設定し **、[OK] をクリックします**。

     ![次世代保護ウィンドウ 11 のイメージ](images/configmgr-select-collection.png)

このタスクを完了すると、ウイルス対策プログラムの構成Windows Defender完了しました。

### <a name="attack-surface-reduction"></a>攻撃面の縮小
Defender for Endpoint の攻撃表面の縮小の柱には、Exploit Guard で使用できる機能セットが含まれています。 攻撃表面の縮小 (ASR) ルール、フォルダー アクセスの制御、ネットワーク保護、エクスプロイト保護。 

これらの機能はすべて監査モードとブロック モードを提供します。 監査モードでは、エンド ユーザーに影響はありません。 これは、追加のテレメトリを収集し、Microsoft Defender セキュリティ センターで利用できる方法です。 展開の目的は、セキュリティ コントロールをブロック モードにステップ バイ ステップで移動する方法です。

監査モードで ASR ルールを設定するには、次の方法を実行します。

1. Microsoft Endpoint Configuration Manager コンソールで、[Assets and Compliance Overview Endpoint Protection] に移動し **\> \> \> 、[Exploit Guard** Windows Defender作成] を **選択します**。

   ![Microsoft Endpoint Configuration Manager console0 のイメージ](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  [攻撃 **表面の縮小] を選択します**。
   

3. ルールを [監査] に **設定し、[** 次へ] を **クリックします**。


    ![Microsoft Endpoint Configuration Manager console1 のイメージ](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. [次へ] をクリックして、新しい Exploit Guard ポリシーを **確認します**。

    ![Microsoft Endpoint Configuration Manager コンソール 2 のイメージ](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. ポリシーが作成されると、[閉じる] を **クリックします**。

    ![Microsoft Endpoint Configuration Manager console3 のイメージ](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Microsoft Endpoint Manager コンソール 1 のイメージ](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  新しく作成したポリシーを右クリックし、[展開] を **選択します**。
    
    ![Microsoft Endpoint Configuration Manager console4 のイメージ](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. ポリシーを新しく作成した Windows 10 コレクションにターゲット設定し **、[OK] をクリックします**。

    ![Microsoft Endpoint Configuration Manager console5 のイメージ](images/0ccfe3e803be4b56c668b220b51da7f7.png)

このタスクを完了すると、監査モードで ASR ルールが正常に構成されました。  
  
ASR ルールがエンドポイントに正しく適用されているかどうかを確認する追加の手順を次に示します。 (これには数分かかる場合があります)


1. Web ブラウザーからに移動します <https://securitycenter.windows.com> 。

2.  左側 **のメニューから [構成** の管理] を選択します。

3. [攻撃 **表面管理] パネルの [攻撃表面の** 管理に移動] をクリックします。 
    
    ![攻撃表面管理のイメージ](images/security-center-attack-surface-mgnt-tile.png)

4. 攻撃表面 **縮小ルール** レポートの [構成] タブをクリックします。 各デバイスの ASR ルール構成の概要と ASR ルールの状態が表示されます。

    ![攻撃表面の縮小ルールレポートのスクリーンショット1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. 各デバイスをクリックすると、ASR ルールの構成の詳細が表示されます。

    ![攻撃表面の縮小ルールレポートのスクリーンショット 2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

詳細 [については、「オプティマイズ ASR ルールの展開と検出」](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   を参照してください。  


#### <a name="set-network-protection-rules-in-audit-mode"></a>監査モードでネットワーク保護ルールを設定します。
1. Microsoft Endpoint Configuration Manager コンソールで、[Assets and Compliance Overview Endpoint Protection] に移動し **\> \> \> 、[Exploit Guard** Windows Defender作成] を **選択します**。

    ![スクリーンショット System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. [ネットワーク **保護] を選択します**。

3. 設定を [監査] に **設定し、[次** へ] を **クリックします**。 

    ![スクリーンショット System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. [次へ] をクリックして、新しい Exploit Guard ポリシーを **確認します**。
    
    ![スクリーンショット Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. ポリシーが作成されると、[閉じる] を **クリックします**。

    ![スクリーンショット Exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. 新しく作成したポリシーを右クリックし、[展開] を **選択します**。

    ![スクリーンショット Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. 新しく作成した Windows 10 コレクションのポリシーを選択し **、[OK] を選択します**。

    ![スクリーンショット Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



このタスクを完了すると、監査モードでネットワーク保護が正常に構成されました。

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a>監査モードでフォルダー アクセスの制御ルールを設定するには、次の操作を行います。

1. Microsoft Endpoint Configuration Manager コンソールで、[Assets and Compliance Overview Endpoint Protection] に移動し **\> \> \> 、[Exploit Guard** Windows Defender作成] を **選択します**。

    ![Microsoft Endpoint Configuration Manager3 のスクリーンショット](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. [フォルダー **アクセスの制御] を選択します**。
    
3. 構成を [監査] に **設定し、[次** へ] を **クリックします**。

    ![Microsoft Endpoint Configuration Manager4 のスクリーンショット](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. [次へ] をクリックして、新しい Exploit Guard ポリシーを **確認します**。

    ![Microsoft Endpoint Configuration Manager5 のスクリーンショット](images/0a6536f2c4024c08709cac8fcf800060.png)

5. ポリシーが作成されると、[閉じる] を **クリックします**。

    ![Microsoft Endpoint Configuration Manager6 のスクリーンショット](images/95d23a07c2c8bc79176788f28cef7557.png)

6. 新しく作成したポリシーを右クリックし、[展開] を **選択します**。

    ![Microsoft Endpoint Configuration Manager7 のスクリーンショット](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  ポリシーを新しく作成した Windows 10 コレクションにターゲット設定し **、[OK] をクリックします**。

    ![Microsoft Endpoint Configuration Manager8 のスクリーンショット](images/0ccfe3e803be4b56c668b220b51da7f7.png)

監査モードでフォルダー アクセスの制御が正常に構成されました。

## <a name="related-topic"></a>関連トピック
- [Microsoft エンドポイント マネージャーを使用したオンボーディング](onboarding-endpoint-manager.md)
