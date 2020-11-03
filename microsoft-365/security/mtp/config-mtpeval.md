---
title: 試用ラボまたはパイロット環境用に Microsoft 365 Defender 柱を構成する
description: 試用ラボやパイロット環境では、microsoft Defender for Office 365、Id 用 microsoft Defender、Id、microsoft Cloud App Security、エンドポイントの Microsoft defender などの Microsoft 365 Defender 柱を構成します。
keywords: Microsoft の脅威保護の評価を構成する、Microsoft の脅威保護の評価の構成、Microsoft の脅威保護パイロットプロジェクトの構成、Microsoft の脅威保護の柱の構成、Microsoft Threat Protection の柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 88db2182ec1a3250d2f4308858026fec97a2f91b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844106"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a>試用ラボまたはパイロット環境用に Microsoft 365 Defender 柱を構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**適用対象:**
- Microsoft 365 Defender


Microsoft 365 Defender 試用ラボまたはパイロット環境を作成して展開するには、3つのフェーズからなるプロセスがあります。

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Microsoft 365 Defender 試用ラボまたはパイロット環境の準備" />
      <br/>フェーズ 1: 準備 </a><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Microsoft 365 Defender 試用ラボまたはパイロット環境の設定" />
      <br/>フェーズ 2: セットアップ </a><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Microsoft 365 Defender 試用ラボまたはパイロット環境およびオンボードエンドポイントの各 Microsoft 365 Defender 柱を構成する" />
      <br/>フェーズ 3: 構成 & オンボード </a><br>
</td>
  </tr>
</table>

現在、構成段階になっています。


正常な展開には、準備が重要です。 この記事では、エンドポイントの Microsoft Defender を展開するための準備として考慮する必要があるポイントについて説明します。


## <a name="microsoft-365-defender-pillars"></a>Microsoft 365 Defender 柱
Microsoft 365 Defender は、4つの柱から構成されています。 1つの柱は、既にネットワーク組織のセキュリティに価値を提供していますが、4つの Microsoft 365 Defender 柱を有効にすることで、組織にとって最大の価値を得ることができます。

![画像 of_Microsoft ユーザーの場合は 365 Defender ソリューション、エンドポイントの場合は microsoft defender、エンドポイントの場合は microsoft defender、クラウドアプリの場合は microsoft Cloud App Security、データについては Microsoft Defender for Office 365](../../media/mtp-eval-31.png)

このセクションでは、以下を構成する方法について説明します。
-   Microsoft Defender for Office 365
-   Id の Microsoft Defender 
-   Microsoft Cloud App Security
-   Microsoft Defender for Endpoint


## <a name="configure-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 を構成する

>[!NOTE]
>Office 365 の Defender が既に有効になっている場合は、この手順をスキップします。 

これらの設定の一部を決定するのに役立つ、 *Office 365 Advanced Threat Protection (ORCA)* という名前の PowerShell モジュールがあります。 テナントで管理者として実行すると、ORCAReport はスパム対策、フィッシング、その他のメッセージの検疫設定の評価を作成するのに役立ちます。 このモジュールはからダウンロードでき https://www.powershellgallery.com/packages/ORCA/ ます。 

1. [Office 365 セキュリティ & コンプライアンスセンター](https://protection.office.com/homepage)の  >  **脅威管理**  >  **ポリシー** に移動します。

   ![Image of_Office 365 Security & コンプライアンスセンターの脅威管理ポリシーページ](../../media/mtp-eval-32.png)
 
2. [ **フィッシング対策** ] をクリックし、[ポリシー名] と [説明] を選択して [ **作成** ] を選択します。 **[次へ]** をクリックします。

   ![Image of_Office 365 Security & コンプライアンスセンターのフィッシング対策ポリシーのページに名前をつけることができます。](../../media/mtp-eval-33.png)

   > [!NOTE]
   > Office 365 の Microsoft Defender で、高度なフィッシング対策ポリシーを編集します。 **Advanced フィッシングしきい値** を **2-アグレッシブ** に変更します。

3. [ **条件の追加** ] ドロップダウンメニューをクリックして、ドメインを受信者のドメインとして選択します。 **[次へ]** をクリックします。

   ![Image of_Office 365 Security & コンプライアンスセンターのフィッシング対策ポリシーページで、アプリケーションの条件を追加することができます。](../../media/mtp-eval-34.png)
 
4. 設定を確認します。 [ **このポリシーを作成** する] をクリックして確認します。 

   ![Image of_Office 365 Security & コンプライアンスセンターのフィッシング対策ポリシーページで設定を確認し、[このポリシーの作成] ボタンをクリックします。](../../media/mtp-eval-35.png)
 
5. [ **安全な添付ファイル** ] を選択し、[ **SharePoint、OneDrive、MICROSOFT Teams で ATP を有効にする** ] オプションを選択します。

   ![Image of_Office 365 Security & SharePoint、OneDrive、Microsoft Teams の ATP を有効にするためのコンプライアンスセンターページ](../../media/mtp-eval-36.png)

6. [+] アイコンをクリックして、新しい安全な添付ファイルポリシーを作成し、ドメインに受信者ドメインとして適用します。 **[保存]** をクリックします。

   ![Image of_Office 365 Security & コンプライアンスセンターページ新しい安全な添付ファイルポリシーを作成する](../../media/mtp-eval-37.png)
 
7. 次に、[ **安全なリンク** ] ポリシーを選択し、鉛筆アイコンをクリックして既定のポリシーを編集します。

8. **[ユーザーが安全なリンクをクリックしたときに追跡** しない] オプションが選択されていない状態で、残りのオプションがオンになっていることを確認します。 詳細については、「 [安全なリンク設定](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 」を参照してください。 **[保存]** をクリックします。 

   ![Image of_Office 365 Security & コンプライアンスセンター] ページで、ユーザーが [セーフ] が選択されていないときに、オプションが追跡されないことを示します。](../../media/mtp-eval-38.png)

9. 次に、 **マルウェア対策** ポリシーを選択し、既定値を選択して、鉛筆アイコンを選択します。

10. [ **設定** ] をクリックし、[はい] を選択して、 **既定の通知テキストを使用** して **マルウェア検出応答** を有効にします。 **一般的な添付ファイルの種類のフィルター** を有効にします。 **[保存]** をクリックします。

    ![イメージ of_Office 365 セキュリティ & コンプライアンスセンターで、マルウェア検出応答が既定の通知で有効になっており、一般的な添付ファイルの種類フィルターが有効になっていることを示します。](../../media/mtp-eval-39.png)
  
11. [ [Office 365 Security & コンプライアンスセンター](https://protection.office.com/homepage)]  >  **Search**  >  [ **監査ログの検索** ] の順に移動し、監査をオンにします。

    ![イメージ of_Office 365 セキュリティ & コンプライアンスセンター] ページで監査ログの検索を有効にする](../../media/mtp-eval-40.png)

12. エンドポイントの Microsoft Defender に Microsoft defender を Office 365 と統合します。 [Office 365 Security & コンプライアンスセンター](https://protection.office.com/homepage)の  >  **脅威管理**  >  **エクスプローラー** に移動し、画面の右上にある **エンドポイント設定に対して Microsoft Defender** を選択します。 [エンドポイントの接続の Defender] ダイアログボックスで、[ **エンドポイントの Microsoft defender への接続** ] をオンにします。

    ![Image of_Office 365 Security & Microsoft Defender をエンドポイント接続に対してオンにできるコンプライアンスセンターページ](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a>Id 用に Microsoft Defender を構成する

>[!NOTE]
>Id に対して Microsoft Defender が既に有効になっている場合は、この手順をスキップします。

1. [Microsoft 365 セキュリティセンター](https://security.microsoft.com/info) > 移動して、[id] に対して [ **その他のリソース** ]  >  **microsoft Defender** を選択します。

   ![イメージ of_Microsoft 365 セキュリティセンターのページ。 Id に対して Microsoft Defender を開くオプションがあります。](../../media/mtp-eval-42.png)

2. [ **作成** ] をクリックして、Microsoft Defender for Identity ウィザードを開始します。 

   ![イメージ of_Microsoft [Id ウィザード] ページで、[作成] ボタンをクリックする必要があります。](../../media/mtp-eval-43.png)

3. [ **Active Directory フォレストに接続するためのユーザー名とパスワードを入力** する] を選択します。  

   ![Id ウェルカムページのイメージ of_Microsoft Defender](../../media/mtp-eval-44.png)

4. Active Directory のオンプレミスの資格情報を入力します。 これには、Active Directory への読み取りアクセス権を持つユーザーアカウントを指定できます。

   ![イメージ of_Microsoft、資格情報を入力する必要がある Id ディレクトリサービスページの Defender](../../media/mtp-eval-45.png)

5. 次に、[ **センサーのセットアップをダウンロード** し、ファイルをドメインコントローラーに転送する] を選択します。

   ![イメージ of_Microsoft の [Id] ページで、[センサーのセットアップのダウンロード] を選択できます。](../../media/mtp-eval-46.png)

6. Id センサーのセットアップ用に Microsoft Defender を実行し、ウィザードのフォローを開始します。

   ![Id センサーウィザードの Microsoft Defender をフォローするには、[Id] ページの [イメージ of_Microsoft Defender] をクリックします。](../../media/mtp-eval-47.png)
 
7. センサー展開の種類で [ **次へ** ] をクリックします。

   ![イメージ of_Microsoft、次のページに移動するには [次へ] をクリックする必要がある Id ページの Defender](../../media/mtp-eval-48.png)
 
8. ウィザードで次に入力する必要があるため、アクセスキーをコピーします。

   ![Id センサーセットアップウィザードの次の Microsoft Defender で入力する必要があるアクセスキーをコピーする必要があるイメージ of_the センサーページ](../../media/mtp-eval-49.png)
 
9. ウィザードにアクセスキーをコピーし、[ **インストール** ] をクリックします。 

   ![イメージ of_Microsoft の Id センサーウィザードページでアクセスキーを指定し、[インストール] ボタンをクリックする必要があります。](../../media/mtp-eval-50.png)

10. ご使用のドメインコントローラーで Id に対して Microsoft Defender が正常に構成されました。

    ![Id センサーウィザードインストールの完了時のイメージ of_Microsoft、[完了] ボタンをクリックする必要があります。](../../media/mtp-eval-51.png)
 
11. [ [Id 設定のための Microsoft defender](https://go.microsoft.com/fwlink/?linkid=2040449) ] セクションで、[* * エンドポイントの場合は * *] を選択し、切り替えをオンにします。 **[保存]** をクリックします。 

    ![[イメージ of_the Microsoft Defender の Id 設定] ページで、エンドポイントに対して Microsoft Defender をオンに切り替える必要があります。](../../media/mtp-eval-52.png)

>[!NOTE]
>Windows Defender ATP は、エンドポイントの Microsoft Defender として再度ブランド化されています。 すべてのポータルにわたる Rebranding の変更は、一貫性を保つために、を展開しています。


## <a name="configure-microsoft-cloud-app-security"></a>Microsoft Cloud App Security を構成する

>[!NOTE]
>Microsoft Cloud App Security を既に有効にしている場合は、この手順をスキップします。 

1. [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **More Resources**  >  **microsoft Cloud App Security** に移動します。

   ![Image of_Microsoft 365 セキュリティセンターページには、Microsoft Cloud App card を参照して、[開く] ボタンをクリックする必要があります。](../../media/mtp-eval-53.png)

2. Id に Microsoft Defender を統合するための情報プロンプトで、[ **id データ統合のための Microsoft defender の有効化** ] を選択します。
  
   ![Image of_the information のメッセージを表示し、id に対して microsoft Defender を統合します。この場合は、Id データ統合のための Microsoft Defender を有効にするリンクを選択します。](../../media/mtp-eval-54.png)

   > [!NOTE]
   > このプロンプトが表示されない場合は、Id データ統合のための Microsoft Defender が既に有効になっていることを意味します。 ただし、わからない場合は、IT 管理者に確認してください。 

3. [ **設定** ] に移動し、[ **id 統合のための Microsoft Defender** ] をオンにして、[ **保存** ] をクリックします。 

   ![[イメージ of_the の設定] ページで、Id 統合のために Microsoft Defender をオンにする必要があります。その後、[保存] をクリックします。](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > Id インスタンス用の新しい Microsoft Defender の場合、この統合トグルは自動的にオンになります。 次の手順に進む前に、Id 統合のための Microsoft Defender が有効になっていることを確認してください。
 
4. [クラウド検出の設定] で、 **エンドポイント統合のための Microsoft Defender** を選択し、統合を有効にします。 **[保存]** をクリックします。

   ![Image of_the microsoft Defender for endpoint 統合のための Microsoft Defender で [承認されていないアプリをブロックする] チェックボックスがオンになっているエンドポイントページ。 [保存] をクリックします。](../../media/mtp-eval-56.png)

5. [クラウド検出の設定] で、[ **ユーザーエンリッチメント** ] を選択して、Azure Active Directory との統合を有効にします。

   ![[エンリッチメントのユーザー識別子を Azure Active Directory ユーザー名で強化する] チェックボックスがオンになっているユーザーのイメージ](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a>エンドポイントの Microsoft Defender を構成する

>[!NOTE]
>エンドポイントに対して Microsoft Defender が既に有効になっている場合は、この手順をスキップします。

1. [Microsoft 365 security center](https://security.microsoft.com/info)  >  **More Resources**  >  **microsoft Defender セキュリティセンター** に移動します。 [ **開く** ] をクリックします。

   ![Microsoft 365 セキュリティセンターページの [イメージ of_Microsoft Defender セキュリティセンター] オプション](../../media/mtp-eval-58.png)
 
2. エンドポイントの Microsoft Defender ウィザードに従います。 **[次へ]** をクリックします。 

   ![Microsoft Defender セキュリティセンターのウェルカムウィザードページ of_the の画像](../../media/mtp-eval-59.png)

3. 推奨されるデータストレージの場所、データ保持ポリシー、組織のサイズ、およびプレビュー機能のオプトインに基づいて選択します。

   ![[イメージ of_the] ページで、データストレージの国、アイテム保持ポリシー、組織のサイズを選択します。 選択が完了したら、[次へ] をクリックします。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > その後、データ保存場所など、一部の設定を変更することはできません。 

   **[次へ]** をクリックします。 

4. [ **続行** ] をクリックすると、エンドポイントテナントに対して Microsoft Defender がプロビジョニングされます。

   ![画像 of_the ページの表示 [続行] ボタンをクリックすると、クラウドインスタンスが作成されます。](../../media/mtp-eval-61.png)

5. エンドポイントをグループポリシー、Microsoft エンドポイントマネージャー、またはエンドポイントの Microsoft Defender に対して実行することによって、エンドポイントをオンボードにします。 簡略化のために、このガイドではローカルスクリプトを使用します。

6. [ **パッケージのダウンロード** ] をクリックし、オンボードスクリプトをエンドポイントにコピーします。

   ![画像 of_page の [パッケージのダウンロード] ボタンをクリックしてオンボードスクリプトをエンドポイントまたはエンドポイントにコピーするように求めるメッセージが表示されます。](../../media/mtp-eval-62.png)

7. エンドポイントで、オンボードスクリプトを管理者として実行し、[Y] を選択します。 

   ![イメージ of_the、オンボードスクリプトを実行し、Y を選択して続行します。](../../media/mtp-eval-63.png)

8. おめでとうございます。第1のエンドポイントを利用しました。

   ![イメージ of_the、第1のエンドポイントを利用することを確認するメッセージが表示されたコマンドライン。 任意のキーを押して続行します。](../../media/mtp-eval-64.png)

9. コピー-エンドポイントの Microsoft Defender ウィザードから検出テストを貼り付けます。

   ![Image of_the [コピー] をクリックして、コマンドプロンプトに貼り付ける必要のある検出テストスクリプトをコピーするための検出テスト手順を実行します。](../../media/mtp-eval-65.png)

10. PowerShell スクリプトを昇格したコマンドプロンプトにコピーして実行します。 

    ![イメージ of_command プロンプトに、管理者特権でのコマンドプロンプトに PowerShell スクリプトをコピーして実行します。](../../media/mtp-eval-66.png)

11. ウィザードから [ **エンドポイントの Microsoft Defender の使用を開始** する] を選択します。

    ![画像 of_the エンドポイントの Microsoft Defender の使用を開始する] をクリックする必要があるウィザードからの確認プロンプト](../../media/mtp-eval-67.png)
 
12. [Microsoft Defender セキュリティセンター](https://securitycenter.windows.com/)を参照してください。 [ **設定** ] に移動し、[ **拡張機能** ] を選択します。 

    ![イメージ of_Microsoft Defender セキュリティセンターの設定] メニューで、高度な機能を選択する必要があります。](../../media/mtp-eval-68.png)

13. **Id の Microsoft Defender** との統合を有効にします。  

    ![イメージ of_Microsoft Defender セキュリティセンターの高度な機能については、Microsoft Defender の Id オプションをオンにする必要があります。](../../media/mtp-eval-69.png)

14. **Office 365 の脅威インテリジェンス** との統合をオンにします。

    ![イメージ of_Microsoft Defender セキュリティセンターの高度な機能である Office 365 脅威インテリジェンスのオプショントグルをオンにする必要がある](../../media/mtp-eval-70.png)

15. **Microsoft Cloud App Security** との統合を有効にします。

    ![イメージ of_Microsoft Defender セキュリティセンターの高度な機能、Microsoft Cloud App Security オプショントグルをオンにする必要がある](../../media/mtp-eval-71.png)

16. 下にスクロールして [ **保存の設定** ] をクリックし、新しい統合を確認します。

    ![クリックする必要があるイメージ of_Save の設定] ボタン](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a>Microsoft 365 Defender サービスを開始する

>[!NOTE]
>2020年6月1日以降、対象となるすべてのテナントに対して Microsoft 365 Defender の機能が自動的に有効になります。 詳細については、 [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) の次の記事を参照してください。 


[Microsoft 365 セキュリティセンター](https://security.microsoft.com/homepage)に移動します。 [ **設定** ] に移動してから、[ **Microsoft 365 Defender** ] を選択します。

![Image of_Microsoft 365 Defender option のスクリーンショット (Microsoft 365 セキュリティセンターの設定ページ) ](../../media/mtp-eval-72b.png) <br>

より包括的なガイダンスについては、「 [Microsoft 365 Defender を有効](mtp-enable.md)にする」を参照してください。 

おめでとうございます。 Microsoft 365 Defender 試用版ラボまたはパイロット環境を作成したばかりです。 これで、Microsoft 365 Defender ユーザーインターフェイスについて理解を深められるようになりました。 次の Microsoft 365 Defender interactive ガイドから学んだ内容を確認し、各ダッシュボードを使用して日常のセキュリティ操作タスクを行う方法について知ることができます。


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

次に、攻撃をシミュレートし、製品間の機能を検出して通知を作成し、エンドポイントへの fileless 攻撃に自動的に応答する方法を確認できます。

## <a name="next-step"></a>次のステップ
|![アタックシミュレーションフェーズ](../../media/mtp/run-sim.png) <br>[アタックシミュレーションフェーズ](mtp-pilot-simulate.md) | Microsoft 365 Defender パイロット環境のアタックシミュレーションを実行します。
|:-------|:-----|
