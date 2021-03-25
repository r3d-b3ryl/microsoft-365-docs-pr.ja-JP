---
title: Microsoft Defender ATP で条件付きアクセスを構成する
description: 条件付きアクセスを実装するために Intune、Microsoft Defender セキュリティ センター、Azure で実行する必要がある手順について説明します。
keywords: 条件付きアクセス、条件付きアクセス、デバイス リスク、リスク レベル、統合、Intune 統合
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0185d7875ac149909ef088d041383a1cf36a8a3a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165863"
---
# <a name="configure-conditional-access-in-microsoft-defender-for-endpoint"></a>Microsoft Defender for Endpoint で条件付きアクセスを構成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

このセクションでは、条件付きアクセスを適切に実装するために必要なすべての手順について説明します。

### <a name="before-you-begin"></a>はじめに
>[!WARNING]
>このシナリオでは、登録されているデバイスAD Azure がサポートされていない点に注意することが重要です。</br>
>Intune に登録されているデバイスだけがサポートされています。


すべてのデバイスが Intune に登録されている必要があります。 Intune にデバイスを登録するには、次のオプションを使用できます。


- IT 管理者: 自動登録を有効にする方法の詳細については、「Windows 登録」 [を参照してください。](https://docs.microsoft.com/intune/windows-enroll#enable-windows-10-automatic-enrollment)
- エンド ユーザー: Intune に Windows 10 デバイスを登録する方法の詳細については、「Intune に Windows 10 デバイスを登録する」 [を参照してください。](https://docs.microsoft.com/intune/quickstart-enroll-windows-device)
- エンド ユーザーの代替: Azure AD ドメインへの参加の詳細については、「How [to: Plan your Azure AD参加実装」を参照してください](https://docs.microsoft.com/azure/active-directory/devices/azureadjoin-plan)。



Microsoft Defender セキュリティ センター、Intune ポータル、Azure セキュリティ ポータルで実行するADがあります。

これらのポータルにアクセスし、条件付きアクセスを実装するために必要な役割に注意することが重要です。
- **Microsoft Defender セキュリティ センター** - 統合を有効にするには、グローバル管理者の役割を持つポータルにサインインする必要があります。
- **Intune** - 管理アクセス許可を持つセキュリティ管理者権限でポータルにサインインする必要があります。 
- **Azure ADポータル** - グローバル管理者、セキュリティ管理者、または条件付きアクセス管理者としてサインインする必要があります。


> [!NOTE]
> Microsoft Intune 環境が必要で、Intune が管理され、Azure AD Windows 10 デバイスに参加している必要があります。

条件付きアクセスを有効にするには、次の手順を実行します。
- 手順 1: Microsoft Defender セキュリティ センターから Microsoft Intune 接続を有効にする
- 手順 2: Intune で Defender for Endpoint 統合を有効にする
- 手順 3: Intune でコンプライアンス ポリシーを作成する
- 手順 4: ポリシーを割り当てる 
- 手順 5: 条件付きアクセス ポリシー AD Azure を作成する


### <a name="step-1-turn-on-the-microsoft-intune-connection"></a>手順 1: Microsoft Intune 接続を有効にする
1. ナビゲーション ウィンドウで、[設定] [**高度**  >  **な機能]**  >  **[Microsoft Intune 接続] を選択します**。
2. Microsoft Intune の設定を [オン] に **切り替える**。
3. [設定 **の保存] をクリックします**。


### <a name="step-2-turn-on-the-defender-for-endpoint-integration-in-intune"></a>手順 2: Intune で Defender for Endpoint 統合を有効にする
1. [Azure portal](https://portal.azure.com) にサインインします。
2. [デバイス **コンプライアンス**  >  **] [Microsoft Defender ATP] を選択します**。
3. **[Windows 10.0.15063+** デバイスの接続] を [Microsoft Defender Advanced Threat Protection] に [オン] に **設定します**。
4. **[保存]** をクリックします。


### <a name="step-3-create-the-compliance-policy-in-intune"></a>手順 3: Intune でコンプライアンス ポリシーを作成する
1. Azure portal [で、[すべてのサービス](https://portal.azure.com)] を選択 **し****、Intune** でフィルター処理し **、[Microsoft Intune] を選択します**。
2. [デバイス **コンプライアンス ポリシー**  >  **] [ポリシー**  >  **の作成] を選択します**。
3. [名前] **と [説明** ] を **入力します**。
4. [**プラットフォーム] で****、[Windows 10 以降] を選択します**。
5. [デバイス **の正常性] 設定** で、[デバイスの脅威レベル] または [デバイスの脅威レベル] の下にあるデバイスを希望する **レベルに設定** します。

   - **セキュリティ** 保護 : このレベルが最も安全です。 デバイスは、既存の脅威を持ち、会社のリソースに引き続きアクセスすることはできません。 脅威が見つかった場合、デバイスは非準拠として評価されます。
   - **低**: 低レベルの脅威だけが存在する場合、デバイスは準拠しています。 中程度または高い脅威レベルを持つデバイスは、準拠していません。
   - **中**: デバイスで検出された脅威が低または中程度の場合、デバイスは準拠しています。 高レベルの脅威が検出された場合、デバイスは非準拠と判断されます。
   - **高**: このレベルは安全性が最も低く、すべての脅威レベルを許可します。 そのため、高、中、低の脅威レベルを持つデバイスは、準拠しているとみなされます。

6. **[OK]** を選択し、[**作成]** を選択して変更を保存します (ポリシーを作成します)。

### <a name="step-4-assign-the-policy"></a>手順 4: ポリシーを割り当てる
1. Azure portal [で、[すべてのサービス](https://portal.azure.com)] を選択 **し****、Intune** でフィルター処理し **、[Microsoft Intune] を選択します**。
2. [**デバイス コンプライアンス ポリシー**  >  **] を選択>** Microsoft Defender ATP コンプライアンス ポリシーを選択します。
3. **[割り当て]** を選択します。
4. ポリシーを割り当てるには、Azure ADグループを含めるか除外します。
5. ポリシーをグループに展開するには、[保存] を **選択します**。 ポリシーの対象となるユーザー デバイスは、コンプライアンスについて評価されます。

### <a name="step-5-create-an-azure-ad-conditional-access-policy"></a>手順 5: 条件付きアクセス ポリシー AD Azure を作成する
1. Azure portal [で、Azure](https://portal.azure.com) **Active Directory 条件付きアクセス**  >  **の新しいポリシー**  >  **を開きます**。
2. ポリシー名を入力 **し、[** ユーザーとグループ **] を選択します**。 [含める] または [除外] オプションを使用してポリシーのグループを追加し、[完了] を **選択します**。
3. [ **クラウド アプリ] を** 選択し、保護するアプリを選択します。 たとえば、[アプリの **選択] を** 選択し **、[365 SharePoint Online] Office 365 Exchange Online** Office **を選択します**。 [**完了**] を選んで変更内容を保存します。

4. [**条件**  >  **クライアント アプリ] を** 選択して、アプリとブラウザーにポリシーを適用します。 たとえば、[はい] **を選択** し、[ **ブラウザー** とモバイル アプリと **デスクトップ クライアント] を有効にします**。 [**完了**] を選んで変更内容を保存します。

5. [許可 **] を** 選択して、デバイスのコンプライアンスに基づいて条件付きアクセスを適用します。 たとえば、[アクセスを許可 **するデバイス**  >  **に準拠としてマークする] を選択します**。 [選択 **] を** 選択して変更を保存します。

6. [ポリシー **を有効にする]** を選択し、[ **作成] を選択して** 変更を保存します。

詳細については [、「Enable Microsoft Defender ATP with Conditional Access in Intune」を参照してください](https://docs.microsoft.com/intune/advanced-threat-protection)。

>Defender for Endpoint を体験してみませんか? [無料試用版にサインアップします。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-belowfoldlink)
