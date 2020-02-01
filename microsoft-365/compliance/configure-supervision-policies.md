---
title: 監督ポリシーを構成する
description: Office 365 の通信監督を構成する
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
- MOE150
titleSuffix: Office 365 Compliance
ms.openlocfilehash: d0bd5411e99471ff326906f65747ec7a6f841545
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596204"
---
# <a name="configure-supervision-policies-in-office-365"></a>Office 365 で監督ポリシーを構成する

>[!IMPORTANT]
>このトピックは、Office 365 サブスクリプションの監督ポリシーの構成に適用されます。 Microsoft 365 サブスクリプションの通信コンプライアンスを構成する場合は、「[Configure communications compliance in Microsoft 365 (preview) (Microsoft 365 で通信コンプライアンスを構成する (プレビュー))](communication-compliance-configure.md)」を参照してください。

監督ポリシーを使って、内部レビューまたは外部レビューによる調査のために従業員の通信をキャプチャします。 監督ポリシーが組織内の通信を監視する方法の詳細については、「[Office 365 の監督ポリシー](supervision-policies.md)」を参照してください。

>[!NOTE]
>監督ポリシーによって監視されるユーザーは、Microsoft 365 E5 コンプライアンス ライセンスか高度なコンプライアンス アドオン付き Office 365 Enterprise E3 ライセンスのいずれかを持っているか、または Office 365 Enterprise E5 サブスクリプションに含まれている必要があります。
>既存の E5 プランを利用しておらず、監督をお試しになりたい場合は、[Office 365 Enterprise E5 の試用版にサインアップしてください](https://go.microsoft.com/fwlink/p/?LinkID=698279)。
  
以下の手順に従って、Office 365 組織に監督を設定して使用します。
  
- **手順 1 (オプション)**: [監督用のグループを設定する](#step-1-set-up-groups-for-supervision-optional)

    監督ポリシーの使用を開始する前に、通信のレビューが必要なユーザーおよびレビューを実行するユーザーを決定します。 少数のユーザーから始めて監督の機能を確認する場合は、グループの設定をスキップできます。

- **手順 2 (必須)**: [組織で監督機能を使用できるようにする](#step-2-make-supervision-available-in-your-organization-required)

    自分がポリシーを設定できるように、自分を監督レビューの役割グループに追加します。 この役割が割り当てられているすべてのユーザーは、Office 365 セキュリティ/コンプライアンス センターの [**監督**] ページにアクセスできます。 レビュー可能なメールが Exchange Online でホストされている場合、各レビュー担当者は [Exchange Online へのリモート PowerShell アクセス](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)が必要です。

- **手順 3 (オプション)**: [カスタムの機密情報の種類と DLP ポリシーでキーワード ディクショナリを使う](#step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional)

    監督ポリシーにカスタムの機密情報の種類またはカスタム キーワードディクショナリが必要な場合は、監督ウィザードを開始する前に作成しておく必要があります。

- **手順 4 (必須)**: [監督ポリシーを設定する](#step-4-set-up-a-supervision-policy-required)

    Office 365 セキュリティ/コンプライアンス センターで監督ポリシーを作成します。 監督ポリシーでは、組織でレビュー対象の通信を定義し、レビューを実行するユーザーを指定します。 通信には、メール、Microsoft Teams の通信、およびサードパーティ製のプラットフォームの通信 (Facebook、Twitter など) が含まれます。 Office 365 組織で作成された監督ポリシーは、Microsoft 365 サブスクリプションの通信監督ではサポートされていません。

- **手順 5**: [通信監督ポリシーをテストする](#step-5-test-your-supervision-policy-optional)

    監督ポリシーをテストして、期待どおりに機能するかどうかを確認します。 コンプライアンス戦略が標準を満たしていることを確認することが重要です。

## <a name="step-1-set-up-groups-for-supervision-optional"></a>手順 1: 監督用のグループを設定する (オプション)

 監督ポリシーを作成するときには、通信がスキャンされるユーザーおよびレビューを実行するユーザーを定義します。 ポリシーでは、メール アドレスを使って、個人または複数人のグループを指定します。 設定を簡単にするために、通信をスキャンされるユーザーのグループと、それらの通信をレビューするユーザーのグループを作成することもできます。 グループを使用している場合は、複数必要になる場合があります。 たとえば、2 つの異なるグループ間の通信を監視する場合や、監督対象ではないグループを指定する場合などです。

次の表を使用して、組織内のグループに通信監督ポリシーを構成することができます。

| **ポリシー メンバー** | **サポートされているグループ** | **サポートされていないグループ** |
|:-----|:-----|:-----|
|監督対象ユーザー <br> 非監督対象ユーザー | 配布グループ <br> Office 365 グループ | 動的配布グループ |
| レビュー担当者 | メールが有効なセキュリティ グループ  | 配布グループ <br> 動的配布グループ |
  
監督対象ユーザーの Office 365 グループを選択すると、ポリシーは共有 Office 365 メールボックスのコンテンツおよびグループに関連付けられた Microsoft Teams チャネルを監視します。 配布リストを選択すると、ポリシーは個々のユーザー メールボックスを監視します。

大規模な企業組織の監督対象ユーザーを管理するには、大規模なグループ全体のユーザーすべてを監視する必要がある場合があります。 PowerShell を使用して、割り当てられたグループのグローバル監督ポリシーの配布グループを構成できます。 これにより、単一のポリシーで数千人のユーザーを監視し、新しい従業員が組織に加入する際に監督ポリシーを最新の状態に保つことができます。

1. 次のプロパティを使用して、グローバル監督ポリシー専用の[配布グループ](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/new-distributiongroup?view=exchange-ps)を作成します。この配布グループが他の目的または他の Office 365 サービスに使用されていないことを確認します。

    - **MemberDepartRestriction = Closed**。 ユーザーが配布グループから自分自身を削除できないようにします。
    - **MemberJoinRestriction = Closed**。 ユーザーが配布グループに自分自身を追加できないようにします。
    - **ModerationEnabled = True**。 このグループに送信されるすべてのメッセージが承認の対象となり、監督ポリシー構成の外部との通信にそのグループが使用されていないことを確認します。

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. 使用されていない [Exchange カスタム属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes?view=exchserver-2019&viewFallbackFrom=exchonline-ww)を選択して、組織の監督ポリシーに追加されたユーザーを追跡します。

3. 定期的なスケジュールで次の PowerShell スクリプトを実行して、ユーザーを監督ポリシーに追加します。

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

グループの設定の詳細については、次の記事を参照してください。

- [配布グループを作成して管理する](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [メールが有効なセキュリティ グループの管理](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups)
- [Overview of Office 365 Groups (Office 365 グループの概要)](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups?view=o365-worldwide)

## <a name="step-2-make-supervision-available-in-your-organization-required"></a>手順 2: 組織で監督機能を使用できるようにする (必須)

Office 365 セキュリティ/コンプライアンス センターのメニュー オプションとして [**監督**] を使えるようにするには、監督レビュー管理者の役割を割り当てられている必要があります。
  
そのためには、自分自身を監督レビュー役割グループのメンバーとして追加するか、役割グループを作成します。
  
### <a name="add-members-to-the-supervisory-review-role-group"></a>監督レビュー役割グループにメンバーを追加する

1. Office 365 組織の管理者アカウントの資格情報を使って、[https://protection.office.com](https://protection.office.com) にサインインします。

2. Office 365 セキュリティ/コンプライアンス センターで、[**アクセス許可**] に移動します。

3. [**監督レビュー**] 役割グループを選び、編集アイコンをクリックします。

4. [**メンバー**] セクションで、組織の通信監督を管理するユーザーを追加します。

### <a name="create-a-new-role-group"></a>新しい役割グループを作成する

1. Office 365 組織の管理者アカウントの資格情報を使って、[https://protection.office.com/permissions](https://protection.office.com/permissions) にサインインします。

2. Office 365 セキュリティ/コンプライアンス センターで、[**アクセス許可**] に移動し、[追加] (**+**) をクリックします。

3. [**役割**] セクションで、[追加] (**+**) をクリックし、[**監督レビュー管理者**] までスクロールします。 この役割を役割グループに追加します。

4. [**メンバー**] セクションで、組織の通信監督を管理するユーザーを追加します。

役割グループとアクセス許可の詳細については、「[Permissions in the Compliance Center (コンプライアンス センターのアクセス許可)](../security/office-365-security/permissions-in-the-security-and-compliance-center.md)」を参照してください。 

### <a name="enable-remote-powershell-access-for-reviewers-if-email-is-hosted-on-exchange-online"></a>レビュー担当者のリモート PowerShell アクセスを有効にします (メールが Exchange Online でホストされている場合)

1. 「[Exchange Online PowerShell へのアクセスを有効または無効にする](https://docs.microsoft.com/powershell/exchange/exchange-online/disable-access-to-exchange-online-powershell)」のガイダンスに従ってください。

## <a name="step-3-create-custom-sensitive-information-types-and-custom-keyword-dictionaries-optional"></a>手順 3: カスタムの機密情報の種類と DLP ポリシーでキーワード ディクショナリを使う (オプション)

監督ポリシー ウィザードで既存のカスタム機密情報の種類またはカスタム キーワード ディクショナリから選択するには、最初にこれらのアイテムを必要に応じて作成する必要があります。

### <a name="create-custom-keyword-dictionarylexicon-optional"></a>カスタム キーワード ディクショナリ/語彙の作成 (オプション)

テキスト エディター (メモ帳など) を使用して、監督ポリシーで監視するキーワード用語を含むファイルを作成します。 各用語が別の行にあることを確認し、**Unicode/UTF-16 (リトル エンディアン)** 形式でファイルを保存します。

### <a name="create-custom-sensitive-information-types"></a>カスタムの機密情報の種類を作成する

1. 新しい機密情報の種類を作成し、Office 365 セキュリティ/コンプライアンス センターでカスタム ディクショナリを追加します。 [**分類**] \> [**機密情報タイプ**] の順に移動し、**新しい機密情報の種類ウィザード**の手順に従います。 ここで、以下の操作をします。

    - 機密情報の種類の名前と説明を定義する
    - 近接性、信頼度、プライマリ パターン要素を定義する
    - 一致する要素の要件としてユーザー ディクショナリをインポートする
    - 選択内容を確認し、機密情報の種類を作成する

    詳細については、「[カスタム機密情報の種類を作成する](create-a-custom-sensitive-information-type.md)」および「[キーワード ディクショナリの作成](create-a-keyword-dictionary.md)」を参照してください

    カスタム ディクショナリ/語彙を作成したら、[Get-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpkeyworddictionary) コマンドレットで構成済みのキーワードを表示したり、[Set-DlpKeywordDictionary](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/set-dlpkeyworddictionary) コマンドレットを使用して用語を追加および削除したりできます。

## <a name="step-4-set-up-a-supervision-policy-required"></a>手順 4: 監督ポリシーを設定する (必須)
  
1. Office 365 組織の管理者アカウントの資格情報を使って、[https://protection.office.com](https://protection.office.com) にサインインします。

2. Office 365 セキュリティ/コンプライアンス センターで、[**監督**] を選択します。
  
3. [**作成**] を選択し、ウィザードに従ってポリシー構成を設定します。 ウィザードを使用して、以下の操作をします。

    - ポリシーに名前と説明を付けます。
    - 除外するユーザーやグループの選択などを含めて、監督するユーザーまたはグループを選択します。
    - 監督ポリシーの[条件](supervision-policies.md#ConditionalSettings)を定義します。 [メッセージ アドレス]、[キーワード]、[ファイルの種類]、および [サイズの一致条件] の中から選ぶことができます。
    - 機密情報の種類を含めるかどうかを選択します。 ここで、既定およびカスタムの機密情報の種類を選択できます。
    - 不快感を与える言語のモデルを有効にするかどうかを選びます。 これにより、メール メッセージの本文で送受信された不適切な言語が検出されます。
    - レビューする通信の割合を定義します。
    - ポリシーのレビュー担当者を選択します。 レビュー担当者は個々のユーザーか、[メールが有効なセキュリティ グループ](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-mail-enabled-security-groups#create-a-mail-enabled-security-group)です。 すべてのレビュー担当者は、Exchange Online でホストされているメールボックスを持っている必要があります。
    - 選択したポリシーを確認し、ポリシーを作成します。

## <a name="step-5-test-your-supervision-policy-optional"></a>手順 5: 監督ポリシーをテストする (オプション)

通信監督ポリシーを作成したら、定義した条件がポリシーによって適切に実施されていることを確認するためのテストの実施をお勧めします。 監督ポリシーに機密情報の種類が含まれている場合は、[データ損失防止 (DLP) ポリシーをテストする](create-test-tune-dlp-policy.md)こともできます。 以下の手順に従って、監督ポリシーをテストします。

1. テストするポリシーで定義されている監督対象ユーザーとしてログインしているメール クライアントまたは Microsoft Teams を開きます。
2. 監督ポリシーで定義した条件を満たすメールまたは Microsoft Teams チャットを送信します。 これは、キーワード、添付ファイルのサイズ、ドメインなどです。ポリシーで構成された条件設定が厳しすぎる、または緩すぎるかどうかを必ず確認してください。

    >[!NOTE]
    >定義されたポリシーの対象となるメールはほぼリアルタイムで処理され、ポリシーの構成後すぐにテストできます。 Microsoft Teams のチャットは、ポリシーで完全に処理されるまでに最大で 24 時間かかる場合があります。 

3. 通信監督ポリシーで指定されたレビュー担当者として、Office 365 テナントにログインします。 [**監督**]  >  [*カスタム ポリシー*]  >  [**開く**] の順に移動して、ポリシーのレポートを表示します。

