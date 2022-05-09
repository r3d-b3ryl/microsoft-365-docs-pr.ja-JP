---
title: オンボーディングまたはオフボーディングの通知ルールを作成する
description: ローカルオンボードまたはオフボード スクリプトが使用されたときに通知を受け取ります。
keywords: オンボード, オフボード, ローカル, スクリプト, 通知, ルール
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0208e21394e350c2b5ffffdca6f8e14ebba227c8
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/25/2022
ms.locfileid: "64476051"
---
# <a name="create-a-notification-rule-when-a-local-onboarding-or-offboarding-script-is-used"></a>ローカルオンボードまたはオフボード スクリプトが使用されている場合に通知ルールを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


ローカルオンボードまたはオフボード スクリプトが使用されると、通知を受け取るように通知ルールを作成します。

## <a name="before-you-begin"></a>開始する前に

次にアクセスできる必要があります。

- Power Automate (少なくともユーザーごとのプラン)。 詳細については、「[Power Automate価格」ページを](https://flow.microsoft.com/pricing/)参照してください。
- Azure Table or SharePoint List or library / SQL DB。

## <a name="create-the-notification-flow"></a>通知フローを作成する

1. [flow.microsoft.com](https://flow.microsoft.com/)。

2. [ **マイ フロー] > [新しい>スケジュール済み] に移動します。空白から移動します**。

   :::image type="content" source="images/new-flow.png" alt-text="フロー" lightbox="images/new-flow.png":::


3. スケジュールされたフローを構築します。
   1. フロー名を入力します。
   2. 開始時刻と時刻を指定します。
   3. 頻度を指定します。 たとえば、5 分ごとです。

   :::image type="content" source="images/build-flow.png" alt-text="通知フロー" lightbox="images/build-flow.png":::

4. +ボタンを選択して、新しいアクションを追加します。 新しいアクションは、Defender for Endpoint セキュリティ センター デバイス (s) API への HTTP 要求になります。 また、すぐに使用できる "WDATP コネクタ" (アクション: "Machines - Get list of machines") に置き換えることができます。

   :::image type="content" source="images/recurrence-add.png" alt-text="繰り返しとアクションの追加" lightbox="images/recurrence-add.png":::

5. 次の HTTP フィールドを入力します。

   - メソッド: デバイスの一覧を取得する値として "GET"。
   - URI: 次のように入力 `https://api.securitycenter.microsoft.com/api/machines`します。
   - 認証: [Active Directory OAuth] を選択します。
   - テナント: サインインしてhttps://portal.azure.com**アプリの登録Azure Active Directory >** に移動し、テナント ID の値を取得します。
   - 観客： `https://securitycenter.onmicrosoft.com/windowsatpservice\`
   - クライアント ID: サインインしてhttps://portal.azure.com**アプリの登録Azure Active Directory >** に移動し、クライアント ID の値を取得します。
   - 資格情報の種類: [シークレット] を選択します。
   - シークレット: サインインしてhttps://portal.azure.com**アプリの登録Azure Active Directory >** に移動し、テナント ID の値を取得します。

    :::image type="content" source="images/http-conditions.png" alt-text="HTTP 条件" lightbox="images/http-conditions.png":::

6. [ **新しいアクションの追加]** を選択して新しい手順を追加し、 **データ操作を** 検索して [ **JSON の解析**] を選択します。

   :::image type="content" source="images/data-operations.png" alt-text="データ操作エントリ" lightbox="images/data-operations.png":::

7. **[コンテンツ**] フィールドに本文を追加します。

   :::image type="content" source="images/parse-json.png" alt-text="解析 JSON セクション" lightbox="images/parse-json.png":::

8. [ **サンプル ペイロードを使用してスキーマを生成する** ] リンクを選択します。

   :::image type="content" source="images/parse-json-schema.png" alt-text="ペイロードを含む解析 JSON" lightbox="images/parse-json-schema.png":::

9. 次の JSON スニペットをコピーして貼り付けます。

    ```json
    {
        "type": "object",
        "properties": {
            "@@odata.context": {
                "type": "string"
            },
            "value": {
                "type": "array",
                "items": {
                    "type": "object",
                    "properties": {
                        "id": {
                            "type": "string"
                        },
                        "computerDnsName": {
                            "type": "string"
                        },
                        "firstSeen": {
                            "type": "string"
                        },
                        "lastSeen": {
                            "type": "string"
                        },
                        "osPlatform": {
                            "type": "string"
                        },
                        "osVersion": {},
                        "lastIpAddress": {
                            "type": "string"
                        },
                        "lastExternalIpAddress": {
                            "type": "string"
                        },
                        "agentVersion": {
                            "type": "string"
                        },
                        "osBuild": {
                            "type": "integer"
                        },
                        "healthStatus": {
                            "type": "string"
                        },
                        "riskScore": {
                            "type": "string"
                        },
                        "exposureScore": {
                            "type": "string"
                        },
                        "aadDeviceId": {},
                        "machineTags": {
                            "type": "array"
                        }
                    },
                    "required": [
                        "id",
                        "computerDnsName",
                        "firstSeen",
                        "lastSeen",
                        "osPlatform",
                        "osVersion",
                        "lastIpAddress",
                        "lastExternalIpAddress",
                        "agentVersion",
                        "osBuild",
                        "healthStatus",
                        "rbacGroupId",
                        "rbacGroupName",
                        "riskScore",
                        "exposureScore",
                        "aadDeviceId",
                        "machineTags"
                    ]
                }
            }
        }
    }

    ```

10. JSON 呼び出しから値を抽出し、オンボードされたデバイスがSharePoint一覧に既に登録されているかどうかを例として確認します。

    - はいの場合、通知はトリガーされません
    - いいえの場合は、新しいオンボードデバイスがSharePoint一覧に登録され、Defender for Endpoint 管理者に通知が送信されます

    :::image type="content" source="images/flow-apply.png" alt-text="各要素へのフローの適用" lightbox="images/flow-apply.png":::

    :::image type="content" source="images/apply-to-each.png" alt-text="Get items 要素へのフローのアプリケーション" lightbox="images/apply-to-each.png":::

11. [ **条件**] で、次の式を追加します。"length(body('Get_items')?['value'])"、条件を 0 に設定します。

    :::image type="content" source="images/apply-to-each-value.png" alt-text="各条件へのフローの適用" lightbox="images/apply-to-each-value.png":::
    :::image type="content" source="images/conditions-2.png" alt-text="条件-1" lightbox="images/conditions-2.png":::
    :::image type="content" source="images/condition3.png" alt-text="条件-2" lightbox="images/condition3.png":::
    :::image type="content" source="images/send-email.png" alt-text="[電子メールの送信] セクション" lightbox="images/send-email.png":::

## <a name="alert-notification"></a>アラート通知

次の図は、電子メール通知の例です。

:::image type="content" source="images/alert-notification.png" alt-text="電子メール通知画面" lightbox="images/alert-notification.png":::

## <a name="tips"></a>ヒント

- lastSeen のみを使用して、ここでフィルター処理できます。
  - 60 分ごと:
    - 過去 7 日間に最後に表示されたすべてのデバイスを使用します。

- デバイスごとに:
  - 最後に表示されたプロパティが [-7 日間、-7days + 60 分] の 1 時間間隔にある場合は、オフボーディングの可能性を警告>します。
  - 最初に確認された場合は、過去 1 時間のオンボードに関するアラートを>します。

このソリューションでは、重複するアラートはありません。多数のデバイスを持つテナントがあります。 これらのデバイスをすべて取得すると、非常にコストが高く、ページングが必要になる場合があります。

次の 2 つのクエリに分割できます。

1. オフボードの場合は、OData $filterを使用してこの間隔のみを取り、条件が満たされた場合にのみ通知します。
2. 過去 1 時間に最後に表示されたすべてのデバイスを取得し、最初に表示されたプロパティを確認します (最初に表示されたプロパティが過去 1 時間にある場合は、最後に表示されたプロパティも存在する必要があります)。
