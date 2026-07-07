```
(async () => {
  try {
    // 取得 access token
    const sessionResponse = await fetch("https://chatgpt.com/api/auth/session", {
      method: "GET",
      credentials: "include"
    });
    const sessionData = await sessionResponse.json();
    const accessToken = sessionData.accessToken;
    if (!accessToken) throw new Error("取得 accessToken 失敗");
    console.log("✅ AccessToken OK");
 
    // 要處理的 ID 清單（已過濾）
    const ids = [
      "59208eb6-ec43-4d87-9289-dbd9e250bdd6",
      "47336c9d-7607-4478-b37c-018049af1e46",
      "2c82c020-e1bc-4363-9502-a6794405f793",
      "9901799e-e832-48b1-9278-9abe73168708",
      "c72dcdb4-63a0-40b7-b0bb-ccce3ca54984",
      "2b636e76-a87b-4222-b536-2dc4a545109f",
      "4779b1d7-3109-4ecb-957f-80262f4d7161",
      "ae67aa09-f3d3-4895-977d-9ca44ed1d996",
      "6daa08c1-59c8-4e06-9bc8-9d7246a63057",
      "521ffc8f-9612-4950-84ed-95773138eca6",
      "ff598c4d-ccaf-40c1-bfaa-cb94565764b1",
      "cf8e512d-1f3b-4603-950c-3d9758a8b435",
      "444437a7-c08b-423e-a2c8-65c17383ba24",
      "eb6642e8-b4a6-4652-9c18-67099f2781cc",
      "a0a16bc9-e1b1-45f0-b269-812b53f60121",
      "8064da55-e484-4ba0-a0bc-db05ee84462b",
      "4fdf7f85-38d1-4eea-aeb9-f50939ffb9d8",
      "e1fbfed6-86a4-49b0-868d-17c396358d57",
      "b49cd6d8-b52d-4c21-93d7-89cc19b5e18e",
      "696cc59b-a475-44b0-b206-4e03593e658f",
      "42822f8a-b530-4649-97ea-83aac42ecf6d",
      "1e595494-2426-4946-b688-58ba75604bcc",
      "83bec9de-395a-44e6-9a30-189508c22b99",
      "5e4c9b31-1b4e-4887-839b-607597928d7c"
    ];
 
    console.log(`🔍 處理 ${ids.length} 個唯一 ID。`);
 
    const successIds = [];
    const failedIds = [];
 
    const sendRequest = async (id) => {
      const url = `https://chatgpt.com/backend-api/accounts/${id}/invites/request`;
      try {
        const response = await fetch(url, {
          method: "POST",
          headers: {
            "accept": "*/*",
            "accept-language": "en-US,en;q=0.9",
            "authorization": `Bearer ${accessToken}`,
            "cache-control": "no-cache",
            "oai-language": "en-US",
            "pragma": "no-cache",
            "sec-fetch-dest": "empty",
            "sec-fetch-mode": "cors",
            "sec-fetch-site": "same-origin"
          },
          referrer: "https://chatgpt.com/k12-verification",
          referrerPolicy: "strict-origin-when-cross-origin",
          body: null,
          mode: "cors",
          credentials: "include"
        });
        const result = await response.json();
        if (response.ok && !result.error) {
          successIds.push(id);
          console.log(`✅ ${id} - 成功`);
        } else {
          failedIds.push(id);
          console.log(`❌ ${id} - 失敗 (${response.status})`);
        }
      } catch (error) {
        failedIds.push(id);
        console.error(`🚫 ${id} - 發生錯誤:`, error.message);
      }
    };
 
    // 依序處理，每次延遲 100ms
    for (const id of ids) {
      await sendRequest(id);
      await new Promise(resolve => setTimeout(resolve, 100));
    }
 
    // 最終報告
    console.log("\n========== 最終報告 ==========");
    console.log(`✅ 成功: ${successIds.length} 個 ID`);
    console.log(`❌ 失敗: ${failedIds.length} 個 ID`);
    if (successIds.length > 0) {
      console.log("\n📋 有效 ID (可重複使用):");
      console.log(successIds.join("\n"));
    }
    if (failedIds.length > 0) {
      console.log("\n📋 失敗 ID (請略過):");
      console.log(failedIds.join("\n"));
    }
    console.log("\n💡 請將有效 ID 複製以供日後使用。");
  } catch (error) {
    console.error("🚨 一般錯誤:", error);
  }
})();



```
